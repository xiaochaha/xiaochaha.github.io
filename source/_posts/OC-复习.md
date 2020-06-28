---
title: OC-复习
date: 2020-06-15 13:55:35
tags:
---

# oc复习

## 面对对象基础

### 面对对象概述

##### 封装、继承、多态

### 类和对象

#####  类的声明和实现

#####  对象的创建

### 方法

##### 方法的定义与使用

### 成员变量

##### 成员变量的定义与引用

##### 成员变量的调用范围

## 面对对象高级

### 封装

##### set、get方法

### 继承

##### 继承、重写

##### super关键字

### 多态

##### 对象的类型转换

## 面对对象的特殊用法

### self关键字

##### 目的、self调用成员变量和方法、注意点：不要在方法里调用本身

### 点语法

##### 点语法的语法，与注意点：不要在set、get方法里使用

### 属性

##### 属性的特性、实现属性

##### assign和retain（弱引用与强引用）

##### 手动内存管理

点击项目名，选择`Build Settings`的`All`下的`Apple LLVM 9.0 -Language-ObjectC`设置为`NO`

##### 僵尸对象监控

点击`Edit Scheme`菜单，选择`Run`的`Diagnostics`下的`Zombie Objects`

### 构造方法

##### 重写init方法

```objective-c
-(id)init
{
	self=[super init];
	if(self!=nil){
		_price=100.0
	}
	return self;
}
```

##### 自定义构造方法

```objective-c
-(id)initWithName:(NSString *)name:(int)age
{
	self=[super init];
	if(self!=nil){
		self.name=name;
		self.age=age;
	}
	return self;
}
```

### description方法

##### 重写description

```objective-c
-(NSString *)desdcription
{
    return[NSString stringWithFormat:@"age=%d,name=%@",_age,_name];
}
```

## 内存管理

### 内存的运作

##### 内存的五大区域

> 栈区域、堆区域、BSS段、数据段、代码段

##### 栈区变量和堆区变量

> 栈区域都是局部变量，离开作用域就会被系统回收
>
> 堆区域是通过指针保存对象在堆的地址，堆区域需要由程序员管理

### 内存管理概述

##### 引用计数器

##### MRC

##### ARC

##### 僵尸对象

### 内存泄漏分析

##### 案例1

##### 案例2

##### 案例3

### @property与内存管理

##### 参数atomic与nonatomic

##### 参数assign与retain

##### 参数readwrite与readonly

##### 参数getter与setter

### 嵌套引用分析

##### 嵌套问题的产生

##### 解决嵌套retain问题

### 自动释放池

##### 自动释放池的特点

## 自动内存管理

### ARC

### ARC机制下单个对象的内存管理

### ARC机制下的循环引用

## 协议与代理