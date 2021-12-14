---
author: "liuqiang"
title: "Js通过url下载文件"
url: "2021/06/20/l下载文件.html"
date: "2021-06-20T16:03:50+08:00"
math: true
description: ""
categories: ["前端"]
tags: ["javaScript"]
---


```javascript
fetch(src).then(res => res.blob().then(blob => {
  let a = document.createElement('a');
  let url = window.URL.createObjectURL(blob);
  a.href = url;
  a.download = name;
  a.click();
  window.URL.revokeObjectURL(url);
}))
```