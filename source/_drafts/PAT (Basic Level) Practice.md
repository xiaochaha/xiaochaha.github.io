---
title: PAT (Basic Level) Practice
date: 2020-02-19 10:48:29
tags: 'C语言基础编程'
categories: 'C语言'
mathjax: true
---

> PAT冲鸭
> 题库：PAT (Basic Level) Practice （中文）

### 1001 害死人不偿命的(3n+1)猜想 (15分)

> 卡拉兹(Callatz)猜想：
>
> 对任何一个正整数 *n*，如果它是偶数，那么把它砍掉一半；如果它是奇数，那么把 (3*n*+1) 砍掉一半。这样一直反复砍下去，最后一定在某一步得到 *n*=1。卡拉兹在 1950 年的世界数学家大会上公布了这个猜想，传说当时耶鲁大学师生齐动员，拼命想证明这个貌似很傻很天真的命题，结果闹得学生们无心学业，一心只证 (3*n*+1)，以至于有人说这是一个阴谋，卡拉兹是在蓄意延缓美国数学界教学与科研的进展……
>
> 我们今天的题目不是证明卡拉兹猜想，而是对给定的任一不超过 1000 的正整数 *n*，简单地数一下，需要多少步（砍几下）才能得到 *n*=1？
>
> ### 输入格式：
>
> 每个测试输入包含 1 个测试用例，即给出正整数 *n* 的值。
>
> ### 输出格式：
>
> 输出从 *n* 计算到 1 需要的步数。
>
> ### 输入样例：
>
> ```in
> 3
> ```
>    
>    ### 输出样例：
> 
>```out
> 5
>```

#### 解题思路



#### 提交代码

```c
#include <stdio.h>
int main() {
	int n;
	int count = 0;
	scanf("%d",&n);
	while(n!=1)
	{
		if (n % 2 != 0) {
			n = (3 * n + 1) / 2;
		}
		else {
			n /=2;
		}
		count++;
	}
	printf("%d", count);
	return 0;
}
```

#### 总结

难度1星

----

### 1002 写出这个数 (20分)

>读入一个正整数 *n*，计算其各位数字之和，用汉语拼音写出和的每一位数字。
>
>### 输入格式：
>
>每个测试输入包含 1 个测试用例，即给出自然数 *n* 的值。这里保证 *n* 小于 10<sup>100</sup>。
>
>### 输出格式：
>
>在一行内输出 *n* 的各位数字之和的每一位，拼音数字间有 1 空格，但一行中最后一个拼音数字后没有空格。
>
>### 输入样例：
>
>```in
>1234567890987654321123456789
>```
>
>### 输出样例：
>
>```out
>yi san wu
>```

#### 解题思路

首先是接收数据，然后是关于位数的计算问题，再中文拼音转换。

#### 提交代码

```c
#include <stdio.h>
void outcome(int n);
int main() {
	int nums[100];
	int sum = 0;
	int n;
	int i=0;
	while ((n=getchar())!='\n')
	{
		n -= 48;
		sum += n;
	}
	while (sum != 0) {
		nums[i] = sum % 10;
		sum /= 10;
		i++;
	}
	for (int j = i-1; j>=0; j--)
	{
		if (j!=i-1)
		{
			printf(" ");
		}
		outcome(nums[j]);
		
	}
    return 0;  
}
void outcome(int n) {
	switch (n)
	{
	case 0:printf("ling"); break;
	case 1:printf("yi"); break;
	case 2:printf("er"); break;
	case 3:printf("san"); break;
	case 4:printf("si"); break;
	case 5:printf("wu"); break;
	case 6:printf("liu"); break;
	case 7:printf("qi"); break;
	case 8:printf("ba"); break;
	case 9:printf("jiu"); break;
	default:
		break;
	}
}

```

#### 总结
----

### 1003 我要通过！ (20分)

>“**答案正确**”是自动判题系统给出的最令人欢喜的回复。本题属于 PAT 的“**答案正确**”大派送 —— 只要读入的字符串满足下列条件，系统就输出“**答案正确**”，否则输出“**答案错误**”。
>
>得到“**答案正确**”的条件是：
>
>1. 字符串中必须仅有 `P`、 `A`、 `T`这三种字符，不可以包含其它字符；
>2. 任意形如 `xPATx` 的字符串都可以获得“**答案正确**”，其中 `x` 或者是空字符串，或者是仅由字母 `A` 组成的字符串；
>3. 如果 `aPbTc` 是正确的，那么 `aPbATca` 也是正确的，其中 `a`、 `b`、 `c` 均或者是空字符串，或者是仅由字母 `A` 组成的字符串。
>
>现在就请你为 PAT 写一个自动裁判程序，判定哪些字符串是可以获得“**答案正确**”的。
>
>### 输入格式：
>
>每个测试输入包含 1 个测试用例。第 1 行给出一个正整数 *n* (<10)，是需要检测的字符串个数。接下来每个字符串占一行，字符串长度不超过 100，且不包含空格。
>
>### 输出格式：
>
>每个字符串的检测结果占一行，如果该字符串可以获得“**答案正确**”，则输出 `YES`，否则输出 `NO`。
>
>### 输入样例：
>
>```in
>8
>PAT
>PAAT
>AAPATAA
>AAPAATAAAA
>xPATx
>PT
>Whatever
>APAAATAA
>```
>
>### 输出样例：
>
>```out
>YES
>YES
>YES
>YES
>NO
>NO
>NO
>NO
>```

#### 解题思路

https://blog.csdn.net/oShuaiFeng/article/details/80622269

#### 提交代码

```c
#include <stdio.h>
#define N 10
#define L 100
void yesOrNo(char str[L]);
int main() {

	int count;
	char str[N][L];
	scanf("%d", &count);
	for (int i = 0; i < count; i++)
	{
		scanf("%s", &str[i]);
		yesOrNo(str[i]);
	}
	return 0;
}

void yesOrNo(char str[L]) {
	//1.只有PAT三个字符
	int flag = 1;
	int p=0, t = 0, a=0;
	int aqnum = 0, aznum = 0, ahnum = 0;
	int locate = 0;
	int i = 0;
	while (str[i]!='\0')
	{
		if (str[i] == 'P') {
			p++;
			locate = 1;
			flag = 0;
		}
		else if (str[i] == 'T') {
			t++;
			locate = 2;
			flag = 0;
		}
		else if (str[i] == 'A') {
			a++;
			flag = 0;
		}
		else flag = 1;
		switch (locate)
		{
		case 0:aqnum++; break;
		case 1:if (str[i]!= 'P')aznum++; break;
		case 2:if (str[i]!= 'T')ahnum++; break;
		default:
			break;
		}
		i++;
	}
		
	if (flag==0 && aqnum*aznum==ahnum && p==1 && t==1 &&a>=1)
	{
		printf("YES\n");
	}
	else {
		printf("NO\n");
	}
}

```

#### 总结

这一题主要难在看懂题意

----

### 标题

>
>
>

#### 解题思路



#### 提交代码

```c

```

#### 总结
----

### 标题

>
>
>

#### 解题思路



#### 提交代码

```c

```

#### 总结
----

### 标题

>
>
>

#### 解题思路



#### 提交代码

```c

```

#### 总结
----

### 标题

>
>
>

#### 解题思路



#### 提交代码

```c

```

#### 总结
----