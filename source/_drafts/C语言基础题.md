---
title: C语言基础题
date: 2019-12-12 22:58:30
tags: 'C语言基础编程'
categories: 'C语言'
---
### 7-1 厘米换算英尺英寸

```c
#include <stdio.h>

int main()
{
	int height=0;
	scanf("%d",&height);
	//height=(foot+inch/12)×0.3048
	int foot=height/100.0/0.3048;//英尺 
	int inch=(height/100.0/0.3048-foot)*12;//英寸 
	printf("%d %d",foot,inch);
	return 0;
}
```

### 7-2 然后是几点

```c
#include <stdio.h>

int main()
{
	int hour=0;//小时 
	int minutes=0;//分钟 
	scanf("%d %d",&hour,&minutes);
	int time=hour/100*60+hour%100+minutes;
	time=time/60*100+time%60;
	printf("%d",time);
}
```

### 7-3 逆序的三位数

```c
#include <stdio.h>

int main()
{
	int num;
	scanf("%d",&num);
	int a=num/100;
	int b=num%100/10;
	int c=num%100%10;
	num=c*100+b*10+a;
	printf("%d",num);
}
```

### 7-4 BCD解密

```
#include <stdio.h>

int main()
{
	int num;
	scanf("%d",&num);
	int a=num/16;
	int b=num%16;
	printf("%d",a*10+b);
}
```

### 7-5 表格输出

```c
#include <stdio.h>

int main()
{
	
	printf("------------------------------------\n");
	printf("Province      Area(km2)   Pop.(10K)\n");
	printf("------------------------------------\n");
	printf("Anhui         139600.00   6461.00\n");
	printf("Beijing        16410.54   1180.70\n");
	printf("Chongqing      82400.00   3144.23\n");
	printf("Shanghai        6340.50   1360.26\n");
	printf("Zhejiang      101800.00   4894.00\n");
	printf("------------------------------------");
}
```

### 7-6 混合类型数据格式化输入

```c
#include <stdio.h>

int main()
{	double a,d;
	int b;
	char c;
	scanf("%lf %d %c %lf",&a,&b,&c,&d);
	printf("%c %d %.2f %.2f",c,b,a,d);
}
```

### 7-7 12-24小时制
```c
#include <stdio.h>

int main()
{
	int a;int b;
	
	scanf("%d:%d",&a,&b);
	if(a>12){
		a-=12;
		printf("%d:%d PM",a,b);	
	}else if(a==12){
		printf("%d:%d PM",a,b);	
	}else{
		printf("%d:%d AM",a,b);
	}		
}
```
### 7-8 超速判断
```c
#include <stdio.h>

int main()
{
	int a;
	scanf("%d",&a);
	if(a>60){
		printf("Speed: %d - Speeding",a);
	}else{
		printf("Speed: %d - OK",a);
	}		
}
```
### 7-9 用天平找小球 
```c
#include <stdio.h>
int main()
{
	int a;int b;int c;
	scanf("%d %d %d",&a,&b,&c);
	printf("%c",a==b?(b==c?'A':'C'):(a==c?'B':'A'));	
}
```