---
title: IDEA搭建Struts2环境
tags: 
- '实战'
- 'Struts2'
- 'IDEA'
categories: 'JavaWEB'
mathjax: true
---

# IDEA搭建Struts2环境

### 首先你要有IDEA、Struts2官网下载的包

{% qnimg 1.png %}

## 创建

{% qnimg 2.png %}

## 加载包

{% qnimg 3.png %}

## 配置tomcat

{% qnimg 4.png %}

### 注意：如果有提示fix就fix

web.xml

```
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">
    <filter>
        <filter-name>struts2</filter-name>
        <filter-class>org.apache.struts2.dispatcher.ng.filter.StrutsPrepareAndExecuteFilter</filter-class>
    </filter>
    <filter-mapping>
        <filter-name>struts2</filter-name>
        <url-pattern>/*</url-pattern>
    </filter-mapping>
</web-app>
```

## 运行

{% qnimg 5.png %}