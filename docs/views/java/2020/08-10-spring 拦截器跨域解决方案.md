---
title: Spring 拦截器实现Cors 跨域并携带sessionid
date: 2020-08-10
tags:
 - java
 - 代码片段
categories:
 - Java
 - spring
---

```java
//option预检查，直接通过请求
if("OPTIONS".equals(request.getMethod())){
returntrue;
}

// 拦截器中动态设置Origin
Private void corsFilter(HttpServletRequestrequest,HttpServletResponseresponse){
String origin=request.getHeader("Origin");
if(StringUtils.isEmpty(origin)){
origin="*";
}
response.addHeader("Access-Control-Allow-Origin",origin);
response.addHeader("Access-Control-Allow-Methods","*");
response.addHeader("Access-Control-Allow-Credentials","true");
response.addHeader("Access-Control-Allow-Headers","*");
}
```
