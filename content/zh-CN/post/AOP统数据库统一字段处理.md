---
author: "liuqiang"
title: "AOP统数据库统一字段处理"
url: "2021/02/02/库统一字段处理.html"
date: "2021-02-04T15:49:31+08:00"
toc: true
math: true
description: ""
categories: ["SpringBoot"]
tags: ["aop"]
---

```java
package com.itvita.norisk.company.config;

import com.itvita.norisk.company.model.dto.CmpUserDto;
import com.itvita.norisk.company.util.SystemUtil;
import org.aspectj.lang.ProceedingJoinPoint;
import org.aspectj.lang.annotation.Around;
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Pointcut;
import org.springframework.beans.BeanWrapper;
import org.springframework.beans.BeanWrapperImpl;
import org.springframework.context.annotation.Configuration;

import java.time.LocalDateTime;

/**
 * @Time: 2021/5/27 11:16
 * @author: liu.q [916000612@qq.com]
 * @des:  统一处理公共数据库字段
 * */
@Aspect
@Configuration
public class SqlAopConfig {

    @Pointcut("execution(* com.itvita.norisk.company.mapper.*.insert(..))")
    public void excudeAddService() {
    }

    @Pointcut("execution(* com.itvita.norisk.company.mapper.*.updateById(..))")
    public void excudeUpdateService() {
    }

    @Around("excudeAddService()")
    public Object addAround(ProceedingJoinPoint thisJoinPoint) {
        try {
            Object[] args = thisJoinPoint.getArgs();
            // myBatis只能传递一个参数
            if (args != null && args.length > 0) {
                Object argument = args[0];
                BeanWrapper beanWrapper = new BeanWrapperImpl(argument);
                CmpUserDto cmpUserDto = SystemUtil.getCmpUserDto();
                beanWrapper.setPropertyValue("createdBy", cmpUserDto.getId());
                beanWrapper.setPropertyValue("createdName", cmpUserDto.getNickName());
                beanWrapper.setPropertyValue("createdTime", LocalDateTime.now());
            }

            return thisJoinPoint.proceed(args);
        } catch (Throwable e) {
            e.printStackTrace();
        }
        return null;
    }

    @Around("excudeUpdateService()")
    public Object UpdAround(ProceedingJoinPoint thisJoinPoint) {
        try {
            Object[] args = thisJoinPoint.getArgs();
            // myBatis只能传递一个参数
            if (args != null && args.length > 0) {
                Object argument = args[0];
                BeanWrapper beanWrapper = new BeanWrapperImpl(argument);
                CmpUserDto cmpUserDto = SystemUtil.getCmpUserDto();
                beanWrapper.setPropertyValue("updatedBy", cmpUserDto.getId());
                beanWrapper.setPropertyValue("updatedName", cmpUserDto.getNickName());
                beanWrapper.setPropertyValue("updatedTime", LocalDateTime.now());
            }

            return thisJoinPoint.proceed(args);
        } catch (Throwable e) {
            e.printStackTrace();
        }
        return null;
    }
}

```