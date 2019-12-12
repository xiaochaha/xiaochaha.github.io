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

