---
title: C语言基础题
date: 2019-12-12 22:58:30
tags: 'C语言基础编程'
categories: 'C语言'
---
> 学c语言，多打打代码
> 题库：PTA- 基础编程题目集

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
	return 0;
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
	return 0;
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
	return 0;
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
	return 0;
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
	return 0;
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
    return 0;
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
    return 0;
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
	return 0;
}
```
### 7-10 计算工资
```c
#include <stdio.h>
int main()
{
	int year;int time;
	double sum;
	double wages;
	scanf("%d %d",&year,&time);
	if(year>4){
		wages=50;
		if(time>40){
			sum=(time-40)*1.5*wages+40*wages;
		}else{
			sum=time*wages;
		}
	}else{
		wages=30;
		if(time>40){
			sum=(time-40)*1.5*wages+40*wages;
		}else{
			sum=time*wages;
		}
	}
	printf("%.2lf",sum);
	return 0;
}
```
### 7-11 分段计算居民水费
```c
#include <stdio.h>
int main()
{
	double x;double y;
	scanf("%lf",&x);
	if(x<15){
		y=4*x/3	;
	}else{
		y=2.5*x-17.5;
	}
	printf("%.2lf",y);
	return 0;
}
```
### 7-12 两个数的简单计算器
```c
#include <stdio.h>
int main()
{	
	int a,c;
	char b;
	int d;
	scanf("%d %c %d",&a,&b,&c);
	switch(b){
		case '+':
			printf("%d",a+c);
			break;
		case '-':
			printf("%d",a-c);
			break;
		case '*':
			printf("%d",a*c);
			break;
		case '/':
			printf("%d",a/c);
			break;
		case '%':
			printf("%d",a%c);
			break;
		default:
			printf("ERROR");
	}
	return 0;
}
```
### 7-13 日K蜡烛图
```c
#include <stdio.h>
int main()
{	
	double Open;
	double High;
	double Low;
	double Close;
	scanf("%lf %lf %lf %lf",&Open,&High,&Low,&Close);
	if(Close>Open){
		printf("R-Hollow");		
	}else if(Close<Open){
		printf("BW-Solid");
	}else{
		printf("R-Cross");
	}
	
	if((Low<Open && Low<Close)&&(High>Open && High>Close)){
		printf(" with Lower Shadow and Upper Shadow");
	}else if(Low<Open && Low<Close){
		printf(" with Lower Shadow");
	}else if(High>Open && High>Close){
		printf(" with Upper Shadow");
	}
	return 0;
}
```
### 7-14 求整数段和
```c
#include <stdio.h>
int main()
{	
    int a,b;
    int count=0,sum=0;
    scanf("%d %d",&a,&b);
    do{
    	printf("%5d",a); 
		count++;   	
    	if(count%5==0&&a!=b){
    		printf("\n");
		}	
		sum+=a;		
    	a++;   	
	}while(a<=b);
	printf("\nSum = %d",sum);
	return 0;
}
```
### 7-15 计算圆周率
```c
#include <stdio.h>
int main()
{	
	double n;int i=0,j=1;
	double sum=1;
	double sum1=1;
	double sum2=1;
	scanf("%lf",&n);
	
    do{
    	i++;
    	j+=2;
    	sum1*=i;
    	sum2*=j;
    	sum+=sum1/sum2;
	}while(sum1/sum2>n);
	printf("%lf",2*sum);
}
```
### 7-16 求符合给定条件的整数集
```
#include <stdio.h>
int main()
{	
	int n;int i,j,k;
	int sum,count=0;
	scanf("%d",&n);
	int arr[4]={n,n+1,n+2,n+3};
	for(i=0;i<4;i++){
		for(j=0;j<4;j++){
			for (k=0;k<4;k++){
				
				if(i!=j&&i!=k&&j!=k){
					count++;
					if(count%6==0)
					printf("%d%d%d\n",arr[i],arr[j],arr[k]);
					else printf("%d%d%d ",arr[i],arr[j],arr[k]);
				}
			}
		}
	}  
}
```
### 7-17 爬动的蠕虫
```
#include <stdio.h>
int main()
{	
	int n,u,d;
	int time,sum=0;
	scanf("%d %d %d",&n,&u,&d);
	while((sum+u)<n){
		sum+=u;
		sum-=d;
		time+=2;
	}
	if(sum+u>=n){
		time++;
	}
	printf("%d",time); 
}
```
----
未完分割线 还剩34+13
