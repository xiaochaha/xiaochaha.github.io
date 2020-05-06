---
title: Struts2的运用案例
tags:
- '实战'
- 'Struts2'
- 'IDEA'
categories: 'JavaWEB'
mathjax: true
---

上课的练习，一共3个案例

废话不多，直接上代码

struts.xml放在最后

## 第一个案例

helloaction.jsp

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>应用案例1</title>
</head>
<body>
<form action="hello.action" method="post">
    请输入姓名：<input name="nameABC"><br>
    <input type="submit" value="提交">
</form>
<br>
</body>

</html>
```

welcome.jsp

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@taglib uri="/struts-tags" prefix="s"%>

<html>
<head>
    <title>应用案例1</title>
</head>
<body>
hello<s:property value="#request.nameKEY"/>
<br>
</body>

</html>
```

StrutsAction

```java
package org.action;

import com.opensymphony.xwork2.ActionContext;
import com.opensymphony.xwork2.ActionSupport;

import java.util.Map;

public class StrutsAction extends ActionSupport {

    private String nameABC;

    public String getNameABC() {
        return nameABC;
    }
    public void setNameABC(String nameABC) {
        this.nameABC = nameABC;
    }
    public String execute() throws Exception {
        Map request = (Map) ActionContext.getContext().get("request");
        // 将当前页面的nameABC的值保存到request对象中，以供下一个页面使用
        // nameKEY是键名，nameABC是键值
        request.put("nameKEY", nameABC);
        return "success";
    }
}

```

## 第二个案例
input.jsp
```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>应用案例2</title>
</head>
<body>
<form action="multiply.action" method="post">
    请输入乘数1：<input name="num1"><br>
    请输入乘数2：<input name="num2"><br>
    <input type="submit" value="求乘积">
</form>
</body>

</html>
```
mulresult.jsp

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@taglib uri="/struts-tags" prefix="s"%>
<html>
<head>
    <title>应用案例2</title>
</head>
<body>
乘数1：<s:property value="#request.num1value" /><br>
乘数2：<s:property value="#request.num2value"/><br>
的乘积结果为：
<s:property value="#request.mulvalue"/>
<br>
</body>

</html>
```

MultiplyAction

```java
package org.action;
import java.util.Map;
import com.opensymphony.xwork2.ActionContext;
import com.opensymphony.xwork2.ActionSupport;
public class MultiplyAction extends ActionSupport {
    private String num1;
    private String num2;

    public String getNum1() {
        return num1;
    }

    public void setNum1(String num1) {
        this.num1 = num1;
    }

    public String getNum2() {
        return num2;
    }

    public void setNum2(String num2) {
        this.num2 = num2;
    }

    @Override
    public String execute() throws Exception {
        //此时程序提示出错，必须调试web工程
        if (num1.trim().length() != 0 && num2.trim().length() != 0) {
            //将jsp页面中的字符串变量转换成整数
            int intNum1 = new Integer(num1).intValue();
            int intNum2 = new Integer(num2).intValue();
            int intMul = intNum1 * intNum2;
            String mul = new Integer(intMul).toString();

            Map req = (Map) ActionContext.getContext().get("request");
            //将2个乘数和计算结果塞入request对象的哈希数组中
            //第一个“键-值”对，键名：num1value，键值：num1
            req.put("num1value", num1);
            //第二个“键-值”对，键名：num2value，键值：num2
            req.put("num2value", num2);
            //第三个“键-值”对，键名：mulvalue，键值：mul
            req.put("mulvalue", mul);
            return "success";
        }else{
            return "error";
        }
    }
}

```

## 第三个案例

Equation.jsp

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>应用案例3</title>
</head>
<body>

题目要求：添加3个字段，a,b,c，求ax^2+bx+c=0方程的解
<br>
<form method="post" action="Solution.action">
    a:<input type="text" name="a"><br>
    b:<input type="text" name="b"><br>
    c: <input type="text" name="c"><br>
    <input type="submit" name="button1" value="求根">
</form>

</body>
</html>
```

result.jsp

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@taglib uri="/struts-tags" prefix="s"%>

<html>
<head>
    <title>应用案例3</title>
</head>
<body>
根1：<s:property value="#request.S1"/><br>
根2：<s:property value="#request.S2"/>
</body>
</html>
```

Equation

```java
package org.action;

import com.opensymphony.xwork2.ActionContext;
import com.opensymphony.xwork2.ActionSupport;

import java.util.Map;

public class Equation extends ActionSupport {
    private String a;
    private String b;
    private String c;

    public String getA() {
        return a;
    }

    public void setA(String a) {
        this.a = a;
    }

    public String getB() {
        return b;
    }

    public void setB(String b) {
        this.b = b;
    }

    public String getC() {
        return c;
    }

    public void setC(String c) {
        this.c = c;
    }

    public String SolveEquation() {
        if (a.trim().length() != 0 && !a.trim().equals("0")) {
            int inta = new Integer(a).intValue();
            int intb = new Integer(b).intValue();
            int intc = new Integer(c).intValue();
            double intd;
            if (intb * intb >= 4 * inta * intc) {
                intd = Math.sqrt(intb * intb - 4 * inta * intc);
            } else {
                intd = Math.sqrt(-(intb * intb - 4 * inta * intc));
            }
            if (intd < 0) {
                return "error";
            } else {
                double solution1 = (-intb + intd) / (2 * inta);
                double solution2 = (-intb - intd) / (2 * inta);
                Map req = (Map) ActionContext.getContext().get("request");
                // 将2个计算结果保存到request的哈希数组中，
                // 供result.jsp网页的s:property控件显示值
                req.put("S1", solution1);
                req.put("S2", solution2);
                return "success";
            }
        } else {
            return "error";
        }
    }
}





```

----

struts.xml

```xml-dtd
<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE struts PUBLIC
        "-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
        "http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>
    <package name="default" extends="struts-default">
        <action name="hello" class="org.action.StrutsAction">
            <result name="success">/welcome.jsp</result>
            <result name="error">/hello.jsp</result>
        </action>
        <action name="multiply" class="org.action.MultiplyAction">
            <result name="success">/mulresult.jsp</result>
            <result name="error">/input.jsp</result>
        </action>
        <action name="Solution" class="org.action.Equation" method="SolveEquation">
            <result name="success">/result.jsp</result>
            <result name="error">/Equation.jsp</result>
        </action>
    </package>
</struts>
```

注意：

如果struts-default报错

添加struts-default.xml

{% qnimg 20200422-1.png %}

比较简单，这里就不展示效果了。