---
title: 'C#-问答'
tags:
---
# C#
## 1. C#的条件语句有哪些？
>- if,else语句
>- switch语句  
## 2. customerValidator自定义验证器有哪些说法？自定义控件有哪些属性？
>**<span style="color:red;">下面对CustomValidator控件说法错误的是（D）。</span>**
     A.能使用自定义的验证函数
     B.可以同时添加客户端验证函数和服务端验证函数
     C.指定客户端验证的属性是ClientValidationFuction
     D.属性runat用来指定服务器端验证函数

## 3. 可以制作动态网页的语言有哪些、后缀？
>语言：ASP(Active Server Pages)，JSP(Java Server Pages)，PHP (Hypertext Preprocessor)
>后缀：.aspx、.asp、.jsp、.php

## 4. 验证控件validatorSummary作用是什么
>**<span style="color:red;">集中显示各个验证结果</span>**

## 5. app_date目录作用是什么
>**App_Data文件夹应该包含应用程序的本地数据存储**。它通常以文件(诸如Microsoft Access或Microsoft SQL Server Express数据库、XML文件、文本文件以及应用程序支持的任何其他文件)形式包含数据存储。该文件夹内容不由ASP.NET处理。该文件夹是ASP.NET提供程序存储自身数据的默认位置。 
共享的数据库文件

## 6. 文件系统网站非常适合学习使用的原因
>不要安装IIS
网站允许放置在任意目录下

## 7.下列控件可以将其他控件包含在其中的？
>Panel控件

## 8. 操作数据库会用到哪些类
>SqlConnection 
SqlDataAdapter
SqlCommand 
SqlDataReader 

## 9. .net有cls作用是什么？通用语言规范作用是什么？
>CLS是公共语言定义(Common Language Specification)
CLS是一种语言必须支持的最小规范要求。如果把公共方法限制为CLS，那么支持.NET的所有语言就都可以使用我们的类！
{% qnimg 20200516-1.png %}
## 10. validatorSummary需要设置哪些属性才能以对话框的形式显示错误
>设置ShowMessgeBox属性为ture

## 11. 连接数据库SqlDataSouce访问哪些数据库
>可以访问数据库：SQLServer、Oracle、ODBC数据库 无法访问：XML

## 12. html标签的基本结构
>```
><HTML> <HEAD> 文件头 </HEAD> <BODY> 文件体 </BODY> </HTML>
>```
## 13. .net和xml紧密结合的好处
>跨平台传送数据

## 14. 装箱和拆箱含义 装箱和拆箱操作的区别
>装箱就是隐式的将一个值型转换为引用型对象。
拆箱就是将一个引用型对象转换成任意值型！
>https://www.cnblogs.com/xiaoshi/archive/2008/05/28/1208902.html

## 15. RadioButtonList和CheckBoxList控件的区别
>RadioButtonList 控件用于创建单选按钮组。
>RadioButtonList 控件中的每个可选项是通过 ListItem 元素来定义的！
>CheckBoxList 控件用于创建多选的复选框组。
>每个 CheckBoxList 控件中的可选项都是由 ListItem 元素定义的！



## 16. 使用数据库 哪个对象与数据源连接
>Connection对象

## 17. asp.net服务器控件类型有哪些
>1.HTML服务器控件
2.Web服务器控件
3.验证控件
4.高级Web服务器控件
https://www.cnblogs.com/jinianjun/archive/2012/01/03/2310964.html

## 18. C#怎么定义枚举类型变量
>```
> public enum Test
>    {
>        男 = 0,
>        女 = 1
>    }
>```

## 19. ado.net系统提供的数据库通用接口的目的是什么
>应用程序设计不必考虑数据库的类型

## 20. c#公共语言规范
>https://www.cnblogs.com/cheatlove/articles/385113.html

## 21. asp.net代码存储方式
>ASP.NET代码共有三种存在形式,即( 嵌入代码 )、( 单一文件 )和( 代码分离 )

## 22. ado.net几个核心对象，基本概念，基本使用方法
>Connection对象
>
>指定某个具体数据源以及提供登陆方式及用户名与密码。
>
>Command对象
>
>执行命令并从数据源中返回结果。其命令的内容可以是Sql语句或者是一个存储过程。Command命令语句可以把Sql语句或者是存储过程通过connection的连接发送给数据源（数据库服务器），然后由数据库服务器执行这些命令，最后再把这些命令的结果通过Connection返回给应用程序。
>
>DataAdapter 数据适配器对象
>
>通过DataAdapter可以将数据库中的数据传输到DataSet中，相当于数据运输的工具。
>
>DataReader对象
>
>用于在数据库中读取数据，一般用于读取一条数据（也可读取多条）。
>
>DataSat
>
>DataSet数据集可以简单理解为一个临时数据库，可以将数据源的数据保存在内存中并且它是独立于任何数据库的。DataSet是由若干个DataTable组成的。
>
>https://www.cnblogs.com/darrenliu/p/4412666.html

## 23. ado session 对象，基本概念，基本使用方法

> **1.Session：每个独立的浏览器都会创建一个独立的Session，不是一台电脑一个Session**
>
> Session存储的数据在当前会话中共享，关闭会话即消失
>
> 特性：Session在20分钟之内如果没有会话操作，则会自动释放
>
> 语法：（1）用Session存值：Session["key名"] = 值;    值，不只是个字符串，可以是对象。
>
> （2）从Session取值：类型 变量名 = (强制转换的类型名)Session["key名"]
>
> （3）释放Session：释放某个Session：Session["key名"]=null；
>
> 　　　　　　　　　 释放所有Session：Session.clear();
>
> 　　　　　　　　　 自动释放：20分钟

## 24. 运行asp.net要预装什么，部署什么

> IIS  + .net framework

## 25. ado\.net Command使用常用属性/方法有哪些

```
Command对象参数
  常用属性如下：
  ParameterName：参数名称，如"@CatID"。
  DbType，SqlType，OleDbType：参数的数据类型。
  Direction：ParameterDirection枚举值。
                   ParameterDirection.Input（默认值）| ParameterDirection.InputOutput |
                   ParameterDirection.Output | ParameterDirection.ReturnValue
方法
ExecuteNonQuery() 返回受命令影响的行数。
ExecuteScalar()   返回第一行第一列（使用与集函数）。如Count(*),Sum,Avg等聚合函数。       ExecuteReader() 返回一个DataReader对象。如果SQL不是查询Select，则返回一个没有任何数据的System.Data.SqlClient.SqlDataReader类型的集合（EOF）。
ExecuteXmlReader()返回一个XmlReader对象。
```
## 26. textbox label button 控件常见属性方法
TextBox 控件用于创建用户可输入文本的文本框。
| 属性                                                         | 描述                                                       | .NET |
| :----------------------------------------------------------- | :--------------------------------------------------------- | :--- |
| [AutoCompleteType](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_autocompletetype.asp) | 规定 TextBox 控件的 AutoComplete 行为。                    | 2.0  |
| [AutoPostBack](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_autopostback.asp) | 布尔值，规定当内容改变时，是否回传到服务器。默认是 false。 | 1.0  |
| CausesValidation                                             | 规定当 Postback 发生时，是否验证页面。                     | 2.0  |
| [Columns](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_columns.asp) | textbox 的宽度。                                           | 1.0  |
| [MaxLength](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_maxlength.asp) | 在 textbox 中所允许的最大字符数。                          | 1.0  |
| [ReadOnly](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_readonly.asp) | 规定能否改变文本框中的文本。                               | 1.0  |
| [Rows](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_rows.asp) | textbox 的高度（仅在 TextMode="Multiline" 时使用）。       | 1.0  |
| runat                                                        | 规定该控件是否是服务器控件。必须设置为 "server"。          |      |
| TagKey                                                       |                                                            |      |
| [Text](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_text.asp) | textbox 的内容。                                           | 1.0  |
| [TextMode](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_textmode.asp) | 规定 TextBox 的行为模式（单行、多行或密码）。              | 1.0  |
| ValidationGroup                                              | 当 Postback 发生时，被验证的控件组。                       |      |
| [Wrap](https://www.w3school.com.cn/aspnet/prop_webcontrol_textbox_wrap.asp) | 布尔值，指示 textbox 的内容是否换行。                      | 1.0  |
| OnTextChanged                                                | 当 textbox 中的文本被更改时，被执行的函数的名称。          |      |
Label 控件用于在页面上显示文本。该文本是可编程的。

| 属性  | 描述                                              |
| :---- | :------------------------------------------------ |
| runat | 规定该控件是一个服务器控件。必须设置为 "server"。 |
| Text  | 在 label 中显示的文本。                           |

Button 控件用于显示按钮。按钮可以是提交按钮或命令按钮。默认地，该控件是提交按钮。

提交按钮没有命令名称，在它被点击时它会把网页传回服务器。可以编写事件句柄来控制提交按钮被点击时执行的动作。

命令按钮拥有命令名称，且允许您在页面上创建多个按钮控件。可以编写事件句柄来控制命令按钮被点击时执行的动作。

| 属性                                                         | 描述                                                         | .NET |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :--- |
| [CausesValidation](https://www.w3school.com.cn/aspnet/prop_webcontrol_button_causesvalidation.asp) | 规定当 Button 被点击时是否验证页面。                         | 1.0  |
| CommandArgument                                              | 有关要执行的命令的附加信息。                                 | 1.0  |
| CommandName                                                  | 与 Command 相关的命令。                                      | 1.0  |
| [OnClientClick](https://www.w3school.com.cn/aspnet/prop_webcontrol_button_onclientclick.asp) | 当按钮被点击时被执行的函数的名称。                           | 2.0  |
| [PostBackUrl](https://www.w3school.com.cn/aspnet/prop_webcontrol_button_postbackurl.asp) | 当 Button 控件被点击时从当前页面传送数据的目标页面 URL。     | 2.0  |
| runat                                                        | 规定该控件是服务器控件。必须设置为 "server"。                | 1.0  |
| [Text](https://www.w3school.com.cn/aspnet/prop_webcontrol_button_text.asp) | 按钮上的文本。                                               | 1.0  |
| [UseSubmitBehavior](https://www.w3school.com.cn/aspnet/prop_webcontrol_button_usesubmitbehavior.asp) | 一个值 ，该值指示 Button 控件使用浏览器的提交机制，还是使用 ASP.NET 的 postback 机制。 | 2.0  |
| [ValidationGroup](https://www.w3school.com.cn/aspnet/prop_webcontrol_button_validationgroup.asp) | 当 Button 控件回传服务器时，该 Button 所属的哪个控件组引发了验证。 | 2.0  |


Web 控件标准属性
```
AccessKey, Attributes, BackColor, BorderColor, BorderStyle, BorderWidth, 
CssClass, Enabled, Font, EnableTheming, ForeColor, Height, IsEnabled, 
SkinID, Style, TabIndex, ToolTip, Width
```
控件标准属性

```
AppRelativeTemplateSourceDirectory, BindingContainer, ClientID, Controls, 
EnableTheming, EnableViewState, ID, NamingContainer, Page, Parent, Site, 
TemplateControl, TemplateSourceDirectory, UniqueID, Visible
```

## 27. 重载与重写的区别

> override 方法重写，把基类的函数重写，方法名和参数类型数量一致
>
> 重载：在同一类中，方法名相同，参数类型或数量不同

## 28. C#基本语法，常见修饰符
>public: 同一程序集(DLL或EXE)中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。
private: 只有同一类或结构中的代码可以访问该类型或成员。
protected: 只有同一类或结构或者此类的派生类中的代码才可以访问该类型或成员。
internal: 同一程序集中的任何代码都可以访问该类型或成员，但的代码不可以。
protected internal: 在一程序集中，protected internal体现的是internal的性质；在其他程序集中，protected internal体现的是protected的性质。

## 29. datareader含义，作用是什么
>DataReader对象是用来读取数据库的最简单方式,它只能读取,不能写入,并且是从头至尾往下读的,无法只读某条数据,但它占用内存小,速度快,有时需要用DataReader的创建

## 30. Codebehind是什么技术
>指定包含与页关联的类的已编译文件的名称。 该特性不能在运行时使用。此特性用于 Web 应用程序项目。
Codebehind 属性并不是一个真正的 ASP.NET 属性，在ASP.NET 文档中是找不到它的。
它其实只是一个 Visual Studio .NET 属性，
Visual Studio .NET 就是借用这个属性来很好地跟踪管理项目中的 Web 窗体和与之相对的代码隐藏文件，
比如当你在设计环境中往 Web 窗体上放入一个服务器控件时，
Visual Studio .NET 将自动找到与该 Web 窗体相对应的代码隐藏文件，并自动插入相关的代码。

## 31. asp.net传递参数的方法有哪些
> - 通过URL链接地址传递
> - POST方式传递
> - Session方式传递
> - Application方式传递
> - 使用Server.Transfer进行传递

## 32. dtd全称有什么作用
>DTD为英文Document Type Definition，中文意思为“文档类型定义”。DTD肩负着两重任务:一方面它帮助你编写合法的代码，另一方面它让浏览器正确地显示器代码。
>https://blog.csdn.net/qingmengwuhen1/article/details/72890459
## 33. 面向对象三个重要特性
>封装
继承
多态
## 34. session cookie分别是什么，有什么
>一：Cookie：
①Cookie是访问某些网站以后在本地存储的一些网站相关的信息，下次再访问的时候减少一些步骤。
②Cookie是服务器在本地机器上存储的小段文本并随每一个请求发送至同一个服务器，是一种在客户端保持状态的方案。
③Cookie是Web服务器发送给浏览器的一块信息。浏览器会在本地文件中给每一个Web服务器存储Cookie。以后浏览器在给特定的Web服务器发请求的时候，同时会发送所有为该服务器存储的Cookie。（Cookie实际上是一小段的文本信息。客户端请求服务器，如果服务器需要记录该用户的状态，就使用response向客户端浏览器颁发一个Cookie。客户端浏览器会把Cookie保存起来。当浏览器再次请求该网站时，浏览器就会把请求地址和Cookie一同给服务器。服务器检查该Cookie，从而判断用户的状态。服务器还可以根据需要修改Cookie的内容。）
二：Session：
①由于HTTP协议是无状态的协议，所以服务端需要记录用户的状态时，就需要用某种机制来识具体的用户，这个机制就是Session。
②Session是另一种记录客户状态的机制。不同的是Cookie保存在客户端浏览器中，而Session保存在服务器上。客户端浏览器访问服务器的时候，服务器把客户端信息以某种形式记录在服务器上，这就是Session。客户端浏览器再次访问时只需要从该Session中查找该客户的状态就可以了。
三：区别：
①Session保存在服务端，Cookie保存在客户端。
②因为Cookie存在客户端，用户可以看见进行编辑伪造，所以安全性低。
③Session对象是在服务器内存中的，而基于窗口的Cookie是在客户端内存中的。
④Cookie不是很安全，别人可以分析存放在本地的Cookie，进行Cookie欺骗；Session会在一定时间内保存在服务器上，当访问增多，会占用服务器性能。
⑤Cookie保存数据不能超过4k，很多浏览器都限制一个站点最多存放20个Cookie。
https://zhuanlan.zhihu.com/p/99330970
## 35. 什么是构造函数，有什么使用约束

构造函数是在定义类对象时有程序自动调用的为类提供初始化操作的函数，其函数名和类名相同，无返回值

作用：在创建类的实例时，给字段赋初值

**五种约束类型
** （1）可以使用“基类约束”（base class constraint）来指定某个基类必须出现在类型实参中。这种约束是通过指定基类名称来实现的。
 （2）可以使用“接口约束”（interface constraint）来指定某个类型实参必须实现一个或多个接口。这种约束是通过指定接口名称来实现的。
 （3）可以要求类型实参必须提供一个无参数的构造函数，这被称为“构造函数约束”（constructor constraint）。它是通过new()指定的。
 （4）可以通过关键字class指定“引用类型约束”（reference type constraint）来限制某个类型实参必须是引用类型。
 （5）可以通过关键字struct指定“值类型约束”（vlaue type constraint）来限制某个类型实参必须是值类型。 

## 36. RegluarExpressValidator控件怎么用？有哪些关键属性？

RegularExpressionValidator控件用于检查输入控件是否与指定的正则表达式的值相匹配。验证类型可以检查各种数字是否正确、输入的字符串位数、输入日期格式和电话号码等等。

用法：public string ValidationExpression { get; set; }

| 属性                 | 描述                                                         |
| -------------------- | ------------------------------------------------------------ |
| ControlToValidate    | 该属性获取或设置要验证的输入控件                             |
| Display              | 该属性获取或设置验证控件中错误信息的显示行为                 |
| ErrorMessage         | 该属性获取或设置验证失败时 ValidationSummary 控件中显示的错误信息的文本 |
| Text                 | 该属性获取或设置验证失败时验证控件中显示的文本               |
| ValidationExpression | 该属性获取或设置确定字段验证模式的正则表达式                 |

 

