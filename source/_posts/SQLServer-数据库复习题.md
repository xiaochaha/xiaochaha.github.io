---
title: 数据库SQLserver复习题
date: 2020-01-03 20:30:52
tags: 'SQLserver复习题'
categories: 
- 'SQLserver'
---

数据库sql server复习题，填空由另外一个同学提供，感谢这位同学。
答案仅供参考，可能有错

### 一、填空题（每题1分，共15分）

1．二个实体对象之间联系有：<span style="color:red;">**一对一**</span>、<span style="color:red;">**一对多**</span>和<span style="color:red;">**多对多**</span>关联。

2．数据库管理系统的结构主要有：<span style="color:red;">**外模式**</span> 、<span style="color:red;">**概念模式**</span>和 <span style="color:red;">**内模式**</span>三种。

3．典型数据模型主要由<span style="color:red;">**层次模型**</span> 、<span style="color:red;">**网状模型**</span>和<span style="color:red;">**关系模型**</span>、<span style="color:red;">**面向对象模型**</span>四种。

4．数据表描述的数据媒体类型有哪几种：<span style="color:red;">**整数、货币、浮点、日期、字符、二进制、图像和文本**</span>。

5．数据完整性主要由、  <span style="color:red;">**实体完整性性**</span>     、<span style="color:red;">**域完整性**</span>        和  <span style="color:red;">**参照完整性**</span>     组成。

6．SQL Server数据库系统采用验证方式有<span style="color:red;">**Windows身份验证**</span>   、<span style="color:red;">**SQL Server身份验证**</span>   、<span style="color:red;">**混合验证三种**</span>   ；

7．DBMS就是管理数据库的系统软件，它具有五大功能：<span style="color:red;">**数据的定义   、   数据组织存储和管理  、    数据操纵功能  、    数据库的事务管理和运行管理     、   数据库的建立和维护**</span> 。

8．SQL Server数据库角色由：<span style="color:red;">**服务器角色、客户端角色、自定义角色**</span>三种。

9．在字符串的匹配操作中，通配符   <span style="color:red;">**%**</span>  表示包含零个或更多字符的任意字符串。

10．目前在国内主流的数据库管理系统软件，请你例举五个：<span style="color:red;">**ACCESS**</span> 、<span style="color:red;">**SQL Server**</span> 、<span style="color:red;">**Oracle**</span> 、<span style="color:red;">**MySQL**</span>  、<span style="color:red;">**PostgreSQL**</span>。

11．信息与数据的关系<span style="color:red;">**信息通常被认为有一定意义的经过加工的数据.数据是信息的载体，它表示了信息**</span>               。

12．数据库管理系统的崇高体系架构上划分，主要有 <span style="color:red;">**表现层、功能层、逻辑层、数据层**</span>层次组成。

13．数据表连接关系由 <span style="color:red;">**左外链接     、 右外链接      、   全外链接     、   交叉链接      、  内链接**</span>五种。

14．数据库E-R图是指 <span style="color:red;">**实体和对象之间的相互关系用图表的方式进行展现       的关系**</span>的关系。

15．在数据管理系统中，变量有 <span style="color:red;">**固定变量    、    局部变量   和 字段名变量**</span>等组成，它们之间主要的区别是 <span style="color:red;">**固定变量不能创建新的变量，是系统固定；局部变量是用户可自定义的变量，作用范围在程序内部；字段名变量定义在数据表中，字段名存储在数据表里不会改变**</span>。

### 二、选择题（每题2分，共24分）

1．SQL语言集数据查询、数据操作、数据定义、和数据控制功能于一体，语句CREATE、DROP、ALTER实现下列哪类功能(<span style="color:red;">**C**</span>)。

A．数据查询      B．数据操纵

C．数据定义      D．数据控制

2. 在<span style="color:red;">非Unicode</span>统一字符编码标准中，可变长度1000个汉字定义方式是（<span style="color:red;">**C**</span>）：

A．varchar(1000)      B．char(1000)

C．varchar(2000)      D．varchar(1000) 

3．在销售表中，计算产品的销售量，应使用的聚合函数(<span style="color:red;">**D**</span>)：

A．Order By 销售产品    B．Computer By销售产品

C．count(销售产品)      D．Sum(销售产品) 

4．在数据表中，需要对某一字段进行域的约束，下列方式中哪一种：(<span style="color:red;">**C**</span>) 。

A．主键（PK）     B．外键(FK)

C．规则        D．唯一性（Unique）

5．管理信息系统指的是：(<span style="color:red;">**D**</span>)。

A．管理信息组成及其各部分之间关系的系统

B．管理信息的计算机软件与硬件结构的组成系统

C．管理信息的人机交互的应用软件系统

D．管理信息收集,传输,加工,储存、维护,并围绕管理目标的人机系统.

6．与 WHERE G BETWEEN 60 AND 100 语句等价的子句是：(<span style="color:red;">**D**</span>) 。

A．WHERE G > 60AND G< 100   B．WHERE G >= 60AND G < 100

C．WHERE G > 60AND G<=100   D．WHERE G>=60AND G < =100

7．要查询STUDENT数据库SC表中姓名含有“王”的学生情况，可用(<span style="color:red;">**A**</span>)命令。

A．SELECT * FROM S WHERE 姓名 LIKE ’%王%’

B．SELECT * FROM STUDENT WHERE 姓名 LIKE ’王’

C．SELECT * FROM S WHERE 姓名 LIKE ’王_’ 

D．SELECT * FROM S WHERE 姓名=’王’

8．数据库的内容更新可由(<span style="color:red;">**C**</span>)操作实现。

　A．CREATE和UPDATE  　　  B．INSERT和SELETE

C．INSERT、UPDATE和DELETE  D．DROP 

9．在视图上不能完成的操作是(<span style="color:red;">**D**</span>) 。

A．在视图上定义新的视图     B．查询操作

C．更新视图           D．在视图上定义新的基本表

10．有一个关系：学生（学号，姓名，系别），规定学号的值域是8个数字组成的字符串，这一规则属于(<span style="color:red;">**C**</span>) 。

A．实体完整性约束        B．参照完整性约束

C．用户自定义完整性约束     D．关键字完整性约束

11．在销售数据中，要统计某一类产品销售总额，并从中选择满足条件的组，实现这一要求选择(<span style="color:red;">**C**</span>)。

A．Sum, Group by         B．Group by, Where 

C．Sum, Group by, Having     D．Sum, Group by, Where

12. 下列哪一种约束必须是非空的(<span style="color:red;">**A**</span>)：

A．主键（PK）          B．外键(FK)   

C．规则（Rule）          D．唯一性（Unique）

 

### 三、基本操作题（每小题5分，共15分）
#### 1．在学生数据表（student）中，表中有学号(sno)、姓名(sname)、性别(sex)、年龄(sage)、班级（Class）字段，写出T-SQL语言的插入操作命令，其中学号为’1005’，姓名叫’王芳’，年龄20岁，性别的女的同学信息。
```sql
INSERT INTO student
(sno,sname,sex,asge)VALUES(1005,'王芳'，20,'女')
```
#### 2．有一学生数据表为student，数据结构与上题想通过，写出T-SQL语言的修改操作命令，同时将王芳同学的年龄与班级修改为“22岁”和“2012级自动化1班 ”。
```sql
UPDATE student SET sage=22,class='2012级自动化1班'
WHERE sname='王芳'
```

#### 3．用T-SQL语言编写创建一个教师数据表，内容包括教师编号（Tid），长度10位，教师名（Tname），4个汉字、性别（Sex），1个汉字，所在学院（Academy），50个汉字长度，以教师编号作为主键。
```sql
CREATE TABLE dbo.teacher(
	Tid INT CONSTRAINT PK_1 PRIMARY KEY,
	Tname VARCHAR(8),
	Sex char(2),
	Academy VARCHAR(100)
)
```

### 四、编程题（3小题，共16分）

#### 1．在药品销售表(xs)中，数据结构有药品名称（ypmc）,药品类别（lb），药品数量（sl）等字段，其中药品类别数据存放是76、77、78、空值，分别表示“处方药品”、“非处方药品”、“医疗器械”，“其它药品”。请写出药品数据查询命令，并要求将药品类别编码数据一次性转换为可读文本数据。（5分）

```sql
--创表添加数据
CREATE TABLE dbo.xs(	
	ypmc VARCHAR(50),
	lb VARCHAR(50),
	sl int
)
insert into xs(ypmc,lb,sl) 
values ('脑白金','76',122),
('云南白药','77',122),
('999皮炎平','78',122),
('止咳糖浆',null,122)

UPDATE xs SET lb=(CASE
	WHEN lb='76' THEN '处方药品'
	WHEN lb='77' THEN '非处方药品'
	WHEN lb='78' THEN '医疗器械'
	ELSE '其它药品'
END)
from xs 


```

#### 2．在学校学籍管理系统中，有三个相关的数据表，分别是学生(Student)、课程表（Course）)和成绩表(Score)。其中三个表的主键分别是Student_id 、Course_id、 Score_id。要求输出选修 “数据库技术与应用” 课程（Course_name）学生的学号（Student_id）、姓名（stu_name）、考试成绩（course_score），并按照降序排列；（5分）

```sql
--注意：用了综合题的例子!需要修改值
SELECT b.cname,a.sno,a.sname,c.grade
FROM Student AS a,Course AS b,Score AS c
WHERE b.cname='数据库技术与应用'AND a.sno=c.scno AND b.cno=c.cno
ORDER BY grade DESC
```

#### 3．查询“数据库技术与应用”课程考试成绩超过平均值的所有学生的学号、姓名、班级、课程名称、成绩，并按照成绩降序排列。（6）

Student(sno、sname、sage、ssex、sclass);

Course(cno、cname、credit、teacher);

Score(scno、cno、sage、grade);

```sql
--注意：用了综合题的例子!需要修改值
SELECT b.cname,a.sno,a.sname,c.grade
FROM Student AS a,Course AS b,Score AS c
WHERE b.cname='数据库技术与应用'AND a.sno=c.scno AND b.cno=c.cno
AND c.grade>(
SELECT AVG(Score.grade) 
FROM Score,Course 
WHERE cname='数据库技术与应用' AND Score.cno=Course.cno
)
ORDER BY grade DESC
```
### 五、综合题（2题，共30分）

#### 1．利用T-SQL语言编写程序，求1+2!+3!+4!+…..+100!；（10分）
```sql
--注意：1+2!+3!+4!+…..+10!
Declare @s int, @i int,@sumi int
Select @s=1,@i=1,@sumi=0
WHILE @i<11 BEGIN
SET @s=@s*@i
SET	@sumi+=@s
SET @i+=1
END
Print @sumi
```

#### 2．设计和编写一个学生学籍管理系统的数据库，假设学生、课程、成绩和老师的数据库关系如下：（20分）

1.Student(sno、sname、sage、ssex、sclass);

2.Course(cno、cname、credit、pubic、author);

3.Score(scno、cno、sage、grade);

4.Teacher(tno、tname、tsex、tage)

  用T-SQL语言实现以下功能：

（1）  根据E-R图，构造其关系图；

（2）  用T-SQL编写创建数据结构表，制定主健（PK）和外健（FK）的字段名；

（3）  求张老师教的“数据库技术与应用”课程的平均成绩；

（4）  求选修张老师课程的学生清单；

（5） 求选修张老师课程的学生成绩清单；

 ```sql
--创建数据表
CREATE TABLE dbo.Student(
	sno INT CONSTRAINT PK_Student PRIMARY KEY,
	sname VARCHAR(50), 
	sage INT,
	ssex CHAR(2),
	sclass VARCHAR(50)
)

CREATE TABLE dbo.Course(
	cno INT CONSTRAINT PK_Course PRIMARY KEY,
	cname VARCHAR(50),
	credit VARCHAR(50),
	pubic VARCHAR(50),
	author VARCHAR(50)
)


CREATE TABLE dbo.Score(
	scno INT CONSTRAINT FK_Student FOREIGN KEY(scno) REFERENCES Student(sno),
	cno INT CONSTRAINT FK_Course FOREIGN KEY(cno) REFERENCES Course(cno),
	grade FLOAT
)


CREATE TABLE dbo.Teacher(
	tno INT CONSTRAINT PK_Teacher PRIMARY KEY,
	tname VARCHAR(50),
	tsex CHAR(2),
	tage INT
)

--添加数据
insert into Student(sno,sname,sage,ssex,sclass) 
values (1,'小超',23,'男','软专1901'),
(2,'小王',23,'男','软专1902'),
(3,'小芳',23,'女','软专1902'),
(4,'小胡',23,'男','软专1901'),
(5,'小红',22,'女','软专1903'),
(6,'小花',22,'女','软专1903')

insert into Teacher(tno,tname,tsex,tage) 
values (1,'吴军','男',33),
(2,'刘艳','男',33),
(3,'马红','女',31),
(4,'李白','男',28),
(5,'杜甫','男',35),
(6,'张老师','女',44)

insert into Course(cno,cname,credit,pubic,author) 
values (1,'数据库技术与应用','学习数据库','123','张老师'),
(2,'JavaScript','学习js','123','王艳'),
(3,'C','学习c','123','杜甫')

insert into Score(scno,cno,grade) 
values (1,1,100),(1,2,100),(1,3,100),
(2,1,90),(2,2,90),(2,3,67),
(3,1,60),(3,2,72),(3,3,90),
(4,1,70),(4,2,88),(4,3,78),
(5,1,88),(5,2,45),(5,3,76),
(6,1,86),(6,2,88),(6,3,81)

--求张老师教的“数据库技术与应用”课程的平均成绩
SELECT AVG(grade) AS 数据库技术与应用平均成绩
FROM Score 
WHERE Score.cno=2

--求选修张老师课程的学生清单
SELECT a.sno,a.sname,a.sage,a.ssex,a.sclass,b.author
FROM Student AS a,Course AS b
WHERE b.author='张老师'

--求选修张老师课程的学生成绩清单
SELECT a.sno,a.sname,a.sage,a.ssex,a.sclass,b.author,c.grade
FROM Student AS a,Course AS b,Score AS c
WHERE b.author='张老师'AND a.sno=c.scno AND b.cno=c.cno
 ```