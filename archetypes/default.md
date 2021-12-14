---
author: "liuqiang"
title: "{{ .TranslationBaseName | title }}"
url: "{{ dateFormat "2006/01/01" .Date }}/{{ lower (substr .TranslationBaseName 6) }}.html"
date: "{{ .Date }}"
toc: true
math: true
description: ""
categories: [""]
tags: [""]
---