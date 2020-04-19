---
title: PTA- 基础编程题目集
date: 2019-12-12 22:58:30
tags: 'C语言基础编程'
categories: 'C语言'
mathjax: true
---
> 学c语言，多打打代码
> 题库：PTA- 基础编程题目集

### 6-1 <span style="color:red;">[循环遍历]</span>简单输出整数 (10分)<span style="color:red;">[√]</span>


>本题要求实现一个函数，对给定的正整数`N`，打印从1到`N`的全部正整数。
>
>### 函数接口定义：
>
>```c++
>void PrintN ( int N );    
>```
>
>其中`N`是用户传入的参数。该函数必须将从1到`N`的全部正整数顺序打印出来，每个数字占1行。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>void PrintN ( int N );
>
>int main ()
>{
>    int N;
>
>    scanf("%d", &N);
>    PrintN( N );
>
>    return 0;
>}
>
>/* 你的代码将被嵌在这里 */
>   
>```
>
>### 输入样例：
>
>```in
>3  
>```
>
>### 输出样例：
>
>```out
>1
>2
>3
>```

#### 解题思路

既然是1到N，循环。

#### 提交代码

```c
void PrintN ( int N ){
	for(int i=1;i<=N;i++)printf("%d\n",i);
}
```

#### 总结

难度1星

----
### 6-2 <span style="color:red;">[循环遍历]</span>多项式求值 (15分)<span style="color:red;">[√]</span>

>本题要求实现一个函数，计算阶数为`n`，系数为`a[0]` ... `a[n]`的多项式$f(x)=\sum_{i=0}^{n}\left(a[i] \times x^{i}\right)$在`x`点的值。
>
>### 函数接口定义：
>
>```c++
>double f( int n, double a[], double x );
>```
>     
>    其中`n`是多项式的阶数，`a[]`中存储系数，`x`是给定点。函数须返回多项式`f(x)`的值。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>#define MAXN 10
>
>double f( int n, double a[], double x );
>
>int main()
>{
>int n, i;
>double a[MAXN], x;
>	
>    scanf("%d %lf", &n, &x);
>    for ( i=0; i<=n; i++ )
>   scanf(“%lf”, &a[i]);
>    printf("%.1f\n", f(n, a, x));
>    return 0;
>     }
>    
>    /* 你的代码将被嵌在这里 */   
>```
>
>### 输入样例：
>
>```in
>2 1.1
>1 2.5 -38.7    
>```
>
>### 输出样例：
>
>```out
>-43.1
>```

#### 解题思路

第一次输入的是阶数和点的值，

第二次输入的是系数，

通过x*x...来获取x的i方。

#### 提交代码

```c
double f( int n, double a[], double x ){
	double sum=a[0];	
	double xi=1.0;
	for(int i=1;i<=n;i++){
		xi*=x;	
		sum+=a[i]*xi;
	}
	return sum;
}
```

#### 总结

难度1星

----
### 6-3 <span style="color:red;">[循环遍历]</span>简单求和 (10分)<span style="color:red;">[√]</span>

>本题要求实现一个函数，求给定的`N`个整数的和。
>
>### 函数接口定义：
>
>```c++
>int Sum ( int List[], int N );
>```
>     
>    其中给定整数存放在数组`List[]`中，正整数`N`是数组元素个数。该函数须返回`N`个`List[]`元素的和。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>#define MAXN 10
>
>int Sum ( int List[], int N );
>
>int main ()
>{
>int List[MAXN], N, i;
>
>scanf("%d", &N);
>    for ( i=0; i<N; i++ )
>   scanf("%d", &List[i]);
>    printf("%d\n", Sum(List, N));
>    
>     return 0;
>    }
>
>    /* 你的代码将被嵌在这里 */
>
>```
>
> ### 输入样例：
>
>```in
>3
>12 34 -5   
>```
>
>### 输出样例：
>
>```out
>41
>```

#### 解题思路

循环

#### 提交代码

```c
int Sum(int List[], int N) {
    int sum=0;
    for (int i = 0; i < N; i++)
    {
        sum += List[i];
    }
    return sum;
}
```

#### 总结

难度1星

----
### 6-4 <span style="color:red;">[循环遍历]</span>求自定类型元素的平均 (10分)<span style="color:red;">[√]</span>

>本题要求实现一个函数，求`N`个集合元素`S[]`的平均值，其中集合元素的类型为自定义的`ElementType`。
>
>### 函数接口定义：
>
>```c++
>ElementType Average( ElementType S[], int N );
>```
>     
>    其中给定集合元素存放在数组`S[]`中，正整数`N`是数组元素个数。该函数须返回`N`个`S[]`元素的平均值，其值也必须是`ElementType`类型。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>#define MAXN 10
>typedef float ElementType;
>
>ElementType Average( ElementType S[], int N );
>
>int main ()
>{
>ElementType S[MAXN];
>int N, i;
>
>    scanf("%d", &N);
>    for ( i=0; i<N; i++ )
>   scanf("%f", &S[i]);
>    printf("%.2f\n", Average(S, N));
>    
>     return 0;
>    }
>
>    /* 你的代码将被嵌在这里 */   
>```
>
>### 输入样例：
>
>```in
>3
>12.3 34 -5   
>```
>
>### 输出样例：
>
>```out
>13.77
>```

#### 解题思路

循环

#### 提交代码

```c
ElementType Average(ElementType S[], int N) {
    ElementType sum = 0;
    for (int i = 0; i < N; i++)
    {
        sum += S[i];
    }
    sum /= N;
    return sum;
}
```

#### 总结

难度1星

----
### 6-5 <span style="color:red;">[循环遍历]</span>求自定类型元素的最大值 (10分)<span style="color:red;">[√]</span>

>本题要求实现一个函数，求`N`个集合元素`S[]`中的最大值，其中集合元素的类型为自定义的`ElementType`。
>
>### 函数接口定义：
>
>```c++
>ElementType Max( ElementType S[], int N );
>```
>     
>    其中给定集合元素存放在数组`S[]`中，正整数`N`是数组元素个数。该函数须返回`N`个`S[]`元素中的最大值，其值也必须是`ElementType`类型。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>#define MAXN 10
>typedef float ElementType;
>
>ElementType Max( ElementType S[], int N );
>
>int main ()
>{
>ElementType S[MAXN];
>int N, i;
>
>    scanf("%d", &N);
>    for ( i=0; i<N; i++ )
>   scanf("%f", &S[i]);
>    printf("%.2f\n", Max(S, N));
>    
>     return 0;
>    }
>
>    /* 你的代码将被嵌在这里 */  
>```
>
>### 输入样例：
>
>```in
>3
>12.3 34 -5   
>```
>
>### 输出样例：
>
>```out
>34.00
>```

#### 解题思路

循环

#### 提交代码

```c
ElementType Max(ElementType S[], int N) {
    ElementType max=S[0];
    for (int i = 0; i < N; i++)
    {
        if (max < S[i])max = S[i];
    }
    return max;
}
```

#### 总结

难度1星

----
### 6-6 <span style="color:red;">[循环遍历]</span>求单链表结点的阶乘和 (15分)<span style="color:red;">[√]</span>

>本题要求实现一个函数，求单链表`L`结点的阶乘和。这里默认所有结点的值非负，且题目保证结果在`int`范围内。
>
>### 函数接口定义：
>
>```c++
>int FactorialSum( List L );
>```
>
>其中单链表`List`的定义如下：
>
>```c++
>typedef struct Node *PtrToNode;
>struct Node {
>    int Data; /* 存储结点数据 */
>    PtrToNode Next; /* 指向下一个结点的指针 */
>};
>typedef PtrToNode List; /* 定义单链表类型 */  
>```
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>#include <stdlib.h>
>
>typedef struct Node *PtrToNode;
>struct Node {
>    int Data; /* 存储结点数据 */
>    PtrToNode Next; /* 指向下一个结点的指针 */
>};
>typedef PtrToNode List; /* 定义单链表类型 */
>
>int FactorialSum( List L );
>
>int main()
>{
>    int N, i;
>    List L, p;
>
>    scanf("%d", &N);
>    L = NULL;
>    for ( i=0; i<N; i++ ) {
>        p = (List)malloc(sizeof(struct Node));//动态分配
>        scanf("%d", &p->Data);
>        p->Next = L;  L = p;
>    }
>    printf("%d\n", FactorialSum(L));
>
>    return 0;
>}
>
>/* 你的代码将被嵌在这里 */   
>```
>
>### 输入样例：
>
>```in
>3
>5 3 6 
>```
>
>### 输出样例：
>
>```out
>846
>```

#### 解题思路

首先要明白单链表是个啥？普通的数组其实是顺序表，是线性表的一种。而链表也是线性表的一种。通过指针来连接，题目中的单链表，就是从头到尾的链表。

不过题目不需要你创建链表，它已经创好了，你只需要求计算。

遍历单链表，得到数字再阶乘。

#### 提交代码

```c
int FactorialSum(List L) {
    int sum=0;
    while(L!=NULL){
        int num = L->Data,n=1;
        for (int i = 1; i <= num; i++)
        {
            n *= i;
        }
        sum += n;
        L = L->Next;
    }
    return sum;
}
```

#### 总结

难度1.5星

----
### 6-7 统计某类完全平方数 (20分)

>本题要求实现一个函数，判断任一给定整数`N`是否满足条件：它是完全平方数，又至少有两位数字相同，如144、676等。
>
>### 函数接口定义：
>
>```c++
>int IsTheNumber ( const int N );    
>```
>
>其中`N`是用户传入的参数。如果`N`满足条件，则该函数必须返回1，否则返回0。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>#include <math.h>
>
>int IsTheNumber ( const int N );
>
>int main()
>{
>    int n1, n2, i, cnt;
>	
>    scanf("%d %d", &n1, &n2);
>    cnt = 0;
>    for ( i=n1; i<=n2; i++ ) {
>        if ( IsTheNumber(i) )
>            cnt++;
>    }
>    printf("cnt = %d\n", cnt);
>
>    return 0;
>}
>
>/* 你的代码将被嵌在这里 */  
>```
>
>### 输入样例：
>
>```in
>105 500  
>```
>
>### 输出样例：
>
>```out
>cnt = 6
>```

#### 解题思路

https://blog.csdn.net/qq_42591058/article/details/88933852

#### 提交代码

```c
int IsTheNumber ( const int N )
{
    int x;
    int m;
    x = sqrt(N);
    m = x * x;
    if(m == N)
    {
        int a[10] = {0};
        int i,j;
        int temp = N;
        while(temp != 0)
        {
            i = temp % 10;
            a[i] += 1;
            temp = temp/10;
        }
        for(j = 0;j < 10; j ++)
        {
            if(a[j] >= 2)
            {
                return 1;
            }
        }
    }
    return 0;
}
```

#### 总结

难度1星

----
### 6-8  <span style="color:red;">[循环遍历]</span>简单阶乘计算 (10分)

>本题要求实现一个计算非负整数阶乘的简单函数。
>
>### 函数接口定义：
>
>```c++
>int Factorial( const int N );
>```
>     
>    其中`N`是用户传入的参数，其值不超过12。如果`N`是非负整数，则该函数必须返回`N`的阶乘，否则返回0。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>int Factorial( const int N );
>
>int main()
>{
>int N, NF;
>	
>scanf("%d", &N);
>    NF = Factorial(N);
>if (NF)  printf("%d! = %d\n", N, NF);
>    else printf("Invalid input\n");
>    
>    return 0;
>    }
>
>    /* 你的代码将被嵌在这里 */
>```
>
>### 输入样例：
>
>     ```in
>    5
>```
>
>### 输出样例：
>
>```out
>5! = 120
>```

#### 解题思路

#### 提交代码

```c
int Factorial(const int N) {
    int sum = 1;
    for (int i = 1; i <= N; i++)
    {
        sum *= i;
    }
    if (N >= 0)return sum;
    else return 0;
}
```

#### 总结

难度1星

----
### 6-9 统计个位数字 (15分)

>本题要求实现一个函数，可统计任一整数中某个位数出现的次数。例如-21252中，2出现了3次，则该函数应该返回3。
>
>### 函数接口定义：
>
>```c++
>int Count_Digit ( const int N, const int D );
>```
>     
>    其中`N`和`D`都是用户传入的参数。`N`的值不超过`int`的范围；`D`是[0, 9]区间内的个位数。函数须返回`N`中`D`出现的次数。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>int Count_Digit ( const int N, const int D );
>
>int main()
>{
>int N, D;
>	
>scanf("%d %d", &N, &D);
>    printf("%d\n", Count_Digit(N, D));
>return 0;
>    }
>    
>    /* 你的代码将被嵌在这里 */
>```
>
>### 输入样例：
>
>     ```in
>    -21252 2
>```
>
>### 输出样例：
>
>```out
>3
>```

#### 解题思路

要注意正负

#### 提交代码

```c
int Count_Digit(const int N, const int D) {
    int count=0;
    int n = N;
    if (n == 0)return 1;
    while (n != 0) {
        int t=n % 10;
        if (t==D&&t>=0)count++;
        else if(t ==-D && t < 0)count++;
        n /= 10;
    }
    return count;
};
```

### 总结

难度1星

----
### 6-10 阶乘计算升级版 (20分)

>本题要求实现一个打印非负整数阶乘的函数。
>
>### 函数接口定义：
>
>```c++
>void Print_Factorial ( const int N );
>```
>     
>    其中`N`是用户传入的参数，其值不超过1000。如果`N`是非负整数，则该函数必须在一行中打印出`N`!的值，否则打印“Invalid input”。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>void Print_Factorial ( const int N );
>
>int main()
>{
>int N;
>	
>scanf("%d", &N);
>    Print_Factorial(N);
>return 0;
>    }
>    
>    /* 你的代码将被嵌在这里 */
>```
>
>### 输入样例：
>
>     ```in
>    15
>```
>
>### 输出样例：
>
>```out
>1307674368000
>```

#### 解题思路

https://www.cnblogs.com/hx97/p/10789237.html

#### 提交代码

```c
void Print_Factorial(const int N) {
    int a[3000],n = N;
    if (N == 0)printf("1");
    else if (N < 0 || N > 1000)printf("Invalid input");
    else {
        int w = 0;
        int i = 0,j=0, k = 0;//i是下标，k是位数
        while (n)//往数组存数据
        {
            a[i++] = n % 10;
            n /= 10;
            k++;
        }
        for (j=N-1; j>1; j--)//从大到小阶乘
        {
            w = 0;
            for (i = 0; i < k; i++) {
                n = a[i] * j + w;
                a[i] = n % 10;
                w = n / 10;
            }
            while (w) {
                a[i++] = w % 10;
                w /=10;
                k++;
            }
        }

        for (int ii = k - 1; ii >= 0; ii--)printf("%d", a[ii]);      
    } 
}
```

### 总结

难度1星

----
### 6-11 求自定类型元素序列的中位数 (25分)

>本题要求实现一个函数，求`N`个集合元素`A[]`的中位数，即序列中第$[(N+1) / 2]$大的元素。其中集合元素的类型为自定义的`ElementType`。
>
>### 函数接口定义：
>
>```c++
>ElementType Median( ElementType A[], int N );   
>```
>
>其中给定集合元素存放在数组`A[]`中，正整数`N`是数组元素个数。该函数须返回`N`个`A[]`元素的中位数，其值也必须是`ElementType`类型。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>#define MAXN 10
>typedef float ElementType;
>
>ElementType Median( ElementType A[], int N );
>
>int main ()
>{
>    ElementType A[MAXN];
>    int N, i;
>
>    scanf("%d", &N);
>    for ( i=0; i<N; i++ )
>        scanf("%f", &A[i]);
>    printf("%.2f\n", Median(A, N));
>
>    return 0;
>}
>
>/* 你的代码将被嵌在这里 */  
>```
>
>### 输入样例：
>
>```in
>3
>12.3 34 -5  
>```
>
>### 输出样例：
>
>```out
>12.30
>```

#### 解题思路

这题用冒泡做最后一个测试点过不去。

希尔排序则可以

https://blog.csdn.net/qq_41521512/article/details/82691758

#### 提交代码

```c
ElementType Median( ElementType A[], int N )
{
  ElementType temp;
  for(int gap= N/2; gap> 0; gap= gap/ 2) //gap是每次排序分组的间隔，每次间隔缩小两倍（其他缩小办法也可以）                                       
  {
    for(int i= gap; i< N; i++)//相当于在同一组内采用直接插入排序
    {
      for(int j= i- gap; j>= 0 && A[j]> A[j+ gap]; j= j- gap)//如果同一组内前一个元素大于相 gap个位置的元素，则两者交换位置
      { 
        temp= A[j];
        A[j]= A[j+ gap];
        A[j+ gap]= temp;
      }
    }
  }
  return A[N/ 2];//返回中间元素
}
```

#### 总结

难度1星

----
### 6-12 判断奇偶性 (10分)

>本题要求实现判断给定整数奇偶性的函数。
>
>### 函数接口定义：
>
>```c++
>int even( int n );   
>```
>
>其中`n`是用户传入的整型参数。当`n`为偶数时，函数返回1；`n`为奇数时返回0。注意：0是偶数。
>
>### 裁判测试程序样例：
>
>```c++
>#include <stdio.h>
>
>int even( int n );
>
>int main()
>{    
>    int n;
>
>    scanf("%d", &n);
>    if (even(n))
>        printf("%d is even.\n", n);
>    else
>        printf("%d is odd.\n", n);
>
>    return 0;
>}
>
>/* 你的代码将被嵌在这里 */
>  
>```
>
>### 输入样例1：
>
>```in
>-6   
>```
>
>### 输出样例1：
>
>```out
>-6 is even.  
>```
>
>### 输入样例2：
>
>```
>5    
>```
>
>### 输出样例2：
>
>```
>5 is odd.
>```

#### 解题思路

ez

#### 提交代码

```c
int even(int n) {
    if (n % 2 != 0)return 0;
    else return 1;
}
```

#### 总结

难度1星

----
### 6-13 折半查找 (15分)

>给一个严格递增数列，函数int Search_Bin(SSTable T, KeyType k)用来二分地查找k在数列中的位置。
>
>### 函数接口定义：
>
>```c++
>int  Search_Bin(SSTable T, KeyType k)  
>```
>
>其中T是有序表，k是查找的值。
>
>### 裁判测试程序样例：
>
>```c++
>#include <iostream>
>using namespace std;
>
>#define MAXSIZE 50
>typedef int KeyType;
>
>typedef  struct                     
>{ KeyType  key;                                             
>} ElemType;  
>
>typedef  struct
>{ ElemType  *R; 
>  int  length;
>} SSTable;                      
>
>void  Create(SSTable &T)
>{ int i;
>  T.R=new ElemType[MAXSIZE+1];
>  cin>>T.length;
>  for(i=1;i<=T.length;i++)
>     cin>>T.R[i].key;   
>}
>
>int  Search_Bin(SSTable T, KeyType k);
>
>int main () 
>{  SSTable T;  KeyType k;
>   Create(T);
>   cin>>k;
>   int pos=Search_Bin(T,k);
>   if(pos==0) cout<<"NOT FOUND"<<endl;
>   else cout<<pos<<endl;
>   return 0;
>}
>
>/* 请在这里填写答案 */    
>```
>
>### 输入格式：
>
>第一行输入一个整数n，表示有序表的元素个数，接下来一行n个数字，依次为表内元素值。 然后输入一个要查找的值。
>
>### 输出格式：
>
>输出这个值在表内的位置，如果没有找到，输出"NOT FOUND"。
>
>### 输入样例：
>
>```in
>5
>1 3 5 7 9
>7   
>```
>
>### 输出样例：
>
>```out
>4  
>```
>
>### 输入样例：
>
>```
>5
>1 3 5 7 9
>10    
>```
>
>### 输出样例：
>
>```
>NOT FOUND
>```

#### 解题思路

要注意当索引值比目标值小的边界问题

#### 提交代码

```c
int  Search_Bin(SSTable T, KeyType k) {
    int a = T.length;
    a /= 2;
    do
    {
        if (T.R[a].key == k) {
            return a;
        }
        else if (T.R[a].key < k) {
            a += (a / 2);
        }
        else if (T.R[a].key > k) {
            a /= 2;
        }
        
        if (a == 0 || a > T.length)
        {
            break;
        }
    } while (1);
    return 0;
}
```

#### 总结

难度1星

----

### 7-1 厘米换算英尺英寸(15分)<span style="color:red;">[√]</span>

> 如果已知英制长度的英尺*foot*和英寸*inch*的值，那么对应的米是$(\text { foot }+\text { inch } / 12) \times 0.3048$。现在，如果用户输入的是厘米数，那么对应英制长度的英尺和英寸是多少呢？别忘了1英尺等于12英寸。
>
> ### 输入格式：
>
> 输入在一行中给出1个正整数，单位是厘米。
>
> ### 输出格式：
>
> 在一行中输出这个厘米数对应英制长度的英尺和英寸的整数值，中间用空格分开。
>
> ### 输入样例：
>
> ```in
> 170 
> ```
>
> ### 输出样例：
>
> ```out
> 5 6
> ```

#### 解题思路

直接用函数来计算

#### 提交代码
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
#### 总结

难度1星

----

### 7-2 然后是几点(15分)<span style="color:red;">[√]</span>

>有时候人们用四位数字表示一个时间，比如1106表示11点零6分。现在，你的程序要根据起始时间和流逝的时间计算出终止时间。
>
>读入两个数字，第一个数字以这样的四位数字表示当前时间，第二个数字表示分钟数，计算当前时间经过那么多分钟后是几点，结果也表示为四位数字。当小时为个位数时，没有前导的零，即5点30分表示为530。注意，第二个数字表示的分钟数可能超过60，也可能是负数。
>
>### 输入格式：
>
>输入在一行中给出2个整数，分别是四位数字表示的起始时间、以及流逝的分钟数，其间以空格分隔。注意：在起始时间中，当小时为个位数时，没有前导的零，即5点30分表示为530；流逝的分钟数可能超过60，也可能是负数。
>
>### 输出格式：
>
>输出四位数字表示的终止时间，当小时为个位数时，没有前导的零。题目保证起始时间和终止时间在同一天内。
>
>### 输入样例：
>
>```in
>1120 110
> ```
>
>### 输出样例：
>
>```out
>1310
>```

#### 解题思路

直接用函数来计算

#### 提交代码
```
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
#### 总结

难度1星

----

### 7-3 逆序的三位数(10分)<span style="color:red;">[√]</span>

> 程序每次读入一个正3位数，然后输出按位逆序的数字。注意：当输入的数字含有结尾的0时，输出不应带有前导的0。比如输入700，输出应该是7。
>
> ### 输入格式：
>
> 每个测试是一个3位的正整数。
>
> ### 输出格式：
>
> 输出按位逆序的数。
>
> ### 输入样例：
>
> ```in
> 123    
> ```
>
> ### 输出样例：
>
> ```out
> 321
> ```

#### 解题思路

搞懂位数是怎么来的就好

#### 提交代码
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
#### 总结

难度1星

----

### 7-4 BCD解密(10分)<span style="color:red;">[√]</span>

> BCD数是用一个字节来表达两位十进制的数，每四个比特表示一位。所以如果一个BCD数的十六进制是0x12，它表达的就是十进制的12。但是小明没学过BCD，把所有的BCD数都当作二进制数转换成十进制输出了。于是BCD的0x12被输出成了十进制的18了！
>
> 现在，你的程序要读入这个错误的十进制数，然后输出正确的十进制数。提示：你可以把18转换回0x12，然后再转换回12。
>
> ### 输入格式：
>
> 输入在一行中给出一个[0, 153]范围内的正整数，保证能转换回有效的BCD数，也就是说这个整数转换成十六进制时不会出现A-F的数字。
>
> ### 输出格式：
>
> 输出对应的十进制数。
>
> ### 输入样例：
>
> ```in
> 18 
> ```
>
> ### 输出样例：
>
> ```out
> 12
> ```

#### 解题思路

进制转换

#### 提交代码
```c
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
#### 总结

难度1星

----

### 7-5 表格输出(5分)<span style="color:red;">[√]</span>

> 本题要求编写程序，按照规定格式输出表格。
>
> ### 输入格式：
>
> 本题目没有输入。
>
> ### 输出格式：
>
> 要求严格按照给出的格式输出下列表格：
>
> ```out
> ------------------------------------
> Province      Area(km2)   Pop.(10K)
> ------------------------------------
> Anhui         139600.00   6461.00
> Beijing        16410.54   1180.70
> Chongqing      82400.00   3144.23
> Shanghai        6340.50   1360.26
> Zhejiang      101800.00   4894.00
> ------------------------------------
> ```

#### 解题思路

ez

#### 提交代码
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
#### 总结

难度0.5星

----

### 7-6 混合类型数据格式化输入(5分)<span style="color:red;">[√]</span>

> 本题要求编写程序，顺序读入浮点数1、整数、字符、浮点数2，再按照字符、整数、浮点数1、浮点数2的顺序输出。
>
> ### 输入格式：
>
> 输入在一行中顺序给出浮点数1、整数、字符、浮点数2，其间以1个空格分隔。
>
> ### 输出格式：
>
> 在一行中按照字符、整数、浮点数1、浮点数2的顺序输出，其中浮点数保留小数点后2位。
>
> ### 输入样例：
>
> ```in
> 2.12 88 c 4.7
> ```
>    
>    ### 输出样例：
> 
>```out
> c 88 2.12 4.70
>```

#### 解题思路

ez

#### 提交代码
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
#### 总结

难度0.5星

----

### 7-7 12-24小时制(15分)<span style="color:red;">[√]</span>

> 编写一个程序，要求用户输入24小时制的时间，然后显示12小时制的时间。
>
> ### 输入格式：
>
> 输入在一行中给出带有中间的`:`符号（半角的冒号）的24小时制的时间，如`12:34`表示12点34分。当小时或分钟数小于10时，均没有前导的零，如`5:6`表示5点零6分。
>
> **提示：**在`scanf`的格式字符串中加入`:`，让`scanf`来处理这个冒号。
>
> ### 输出格式：
>
> 在一行中输出这个时间对应的12小时制的时间，数字部分格式与输入的相同，然后跟上空格，再跟上表示上午的字符串`AM`或表示下午的字符串`PM`。如`5:6 PM`表示下午5点零6分。注意，在英文的习惯中，中午12点被认为是下午，所以24小时制的`12:00`就是12小时制的`12:0 PM`；而0点被认为是第二天的时间，所以是`0:0 AM`。
>
> ### 输入样例：
>
> ```in
> 21:11   
> ```
>
> ### 输出样例：
>
> ```out
> 9:11 PM
> ```

#### 解题思路

条件判断

#### 提交代码
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
#### 总结

难度1星

----

### 7-8 超速判断(10分)<span style="color:red;">[√]</span>

> 模拟交通警察的雷达测速仪。输入汽车速度，如果速度超出60 mph，则显示“Speeding”，否则显示“OK”。
>
> ### 输入格式：
>
> 输入在一行中给出1个不超过500的非负整数，即雷达测到的车速。
>
> ### 输出格式：
>
> 在一行中输出测速仪显示结果，格式为：`Speed: V - S`，其中`V`是车速，`S`或者是`Speeding`、或者是`OK`。
>
> ### 输入样例1：
>
> ```in
> 40   
> ```
>
> ### 输出样例1：
>
> ```out
> Speed: 40 - OK    
> ```
>
> ### 输入样例2：
>
> ```in
> 75
> ```
>
> ### 输出样例2：
>
> ```out
> Speed: 75 - Speeding
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1星

----

### 7-9 用天平找小球(10分) <span style="color:red;">[√]</span>

> 三个球A、B、C，大小形状相同且其中有一个球与其他球重量不同。要求找出这个不一样的球。
>
> ### 输入格式：
>
> 输入在一行中给出3个正整数，顺序对应球A、B、C的重量。
>
> ### 输出格式：
>
> 在一行中输出唯一的那个不一样的球。
>
> ### 输入样例：
>
> ```in
> 1 1 2  
> ```
>
> ### 输出样例：
>
> ```out
> C
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1星

----

### 7-10 计算工资(15分)<span style="color:red;">[√]</span>

> 某公司员工的工资计算方法如下：一周内工作时间不超过40小时，按正常工作时间计酬；超出40小时的工作时间部分，按正常工作时间报酬的1.5倍计酬。员工按进公司时间分为新职工和老职工，进公司不少于5年的员工为老职工，5年以下的为新职工。新职工的正常工资为30元/小时，老职工的正常工资为50元/小时。请按该计酬方式计算员工的工资。
>
> ### 输入格式：
>
> 输入在一行中给出2个正整数，分别为某员工入职年数和周工作时间，其间以空格分隔。
>
> ### 输出格式：
>
> 在一行输出该员工的周薪，精确到小数点后2位。
>
> ### 输入样例1：
>
> ```in
> 5 40  
> ```
>
> ### 输出样例1：
>
> ```out
> 2000.00   
> ```
>
> ### 输入样例2：
>
> ```
> 3 50
> ```
>
> ### 输出样例2：
>
> ```
> 1650.00
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1.5星

### 7-11 分段计算居民水费(10分)<span style="color:red;">[√]</span>

> 为鼓励居民节约用水，自来水公司采取按用水量阶梯式计价的办法，居民应交水费*y*（元）与月用水量*x*（吨）相关：当*x*不超过15吨时，*y*=4*x*/3；超过后，*y*=2.5*x*−17.5。请编写程序实现水费的计算。
>
> ### 输入格式：
>
> 输入在一行中给出非负实数*x*。
>
> ### 输出格式：
>
> 在一行输出应交的水费，精确到小数点后2位。
>
> ### 输入样例1：
>
> ```in
> 12   
> ```
>
> ### 输出样例1：
>
> ```out
> 16.00   
> ```
>
> ### 输入样例2：
>
> ```
> 16   
> ```
>
> ### 输出样例2：
>
> ```
> 22.50
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1星

----

### 7-12 两个数的简单计算器(10分)<span style="color:red;">[√]</span>

> 本题要求编写一个简单计算器程序，可根据输入的运算符，对2个整数进行加、减、乘、除或求余运算。题目保证输入和输出均不超过整型范围。
>
> ### 输入格式：
>
> 输入在一行中依次输入操作数1、运算符、操作数2，其间以1个空格分隔。操作数的数据类型为整型，且保证除法和求余的分母非零。
>
> ### 输出格式：
>
> 当运算符为`+`、`-`、`*`、`/`、`%`时，在一行输出相应的运算结果。若输入是非法符号（即除了加、减、乘、除和求余五种运算符以外的其他符号）则输出`ERROR`。
>
> ### 输入样例1：
>
> ```in
> -7 / 2    
> ```
>
> ### 输出样例1：
>
> ```out
> -3   
> ```
>
> ### 输入样例2：
>
> ```in
> 3 & 6
> ```
>
> ### 输出样例2：
>
> ```out
> ERROR
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1星

----

### **7-13** **日K蜡烛图** (15分)<span style="color:red;">[√]</span>

> 股票价格涨跌趋势，常用蜡烛图技术中的K线图来表示，分为按日的日K线、按周的周K线、按月的月K线等。以日K线为例，每天股票价格从开盘到收盘走完一天，对应一根蜡烛小图，要表示四个价格：开盘价格Open（早上刚刚开始开盘买卖成交的第1笔价格）、收盘价格Close（下午收盘时最后一笔成交的价格）、中间的最高价High和最低价Low。
>
> 如果Close<Open，表示为“BW-Solid”（即“实心蓝白蜡烛”）；如果Close>Open，表示为“R-Hollow”（即“空心红蜡烛”）；如果Open等于Close，则为“R-Cross”（即“十字红蜡烛”）。如果Low比Open和Close低，称为“Lower Shadow”（即“有下影线”），如果High比Open和Close高，称为“Upper Shadow”（即“有上影线”）。请编程序，根据给定的四个价格组合，判断当日的蜡烛是一根什么样的蜡烛。
>
> ### 输入格式：
>
> 输入在一行中给出4个正实数，分别对应Open、High、Low、Close，其间以空格分隔。
>
> ### 输出格式：
>
> 在一行中输出日K蜡烛的类型。如果有上、下影线，则在类型后加上`with 影线类型`。如果两种影线都有，则输出`with Lower Shadow and Upper Shadow`。
>
> ### 输入样例1：
>
> ```in
> 5.110 5.250 5.100 5.105   
> ```
>
> ### 输出样例1：
>
> ```out
> BW-Solid with Lower Shadow and Upper Shadow
> ```
>
> ### 输入样例2：
>
> ```in
> 5.110 5.110 5.110 5.110  
> ```
>
> ### 输出样例2：
>
> ```out
> R-Cross  
> ```
>
> ### 输入样例3：
>
> ```in
> 5.110 5.125 5.112 5.126
> ```
>
> ### 输出样例3：
>
> ```out
> R-Hollow
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1.5星

----

### 7-14 求整数段和(15分)<span style="color:red;">[√]</span>

> 给定两个整数*A*和*B*，输出从*A*到*B*的所有整数以及这些数的和。
>
> ### 输入格式：
>
> 输入在一行中给出2个整数*A*和*B*，其中$-100 \leq A \leq B \leq 100$，其间以空格分隔。
>
> ### 输出格式：
>
> 首先顺序输出从*A*到*B*的所有整数，每5个数字占一行，每个数字占5个字符宽度，向右对齐。最后在一行中按`Sum = X`的格式输出全部数字的和`X`。
>
> ### 输入样例：
>
> ```in
> -3 8   
> ```
>
> ### 输出样例：
>
> ```out
>    -3   -2   -1    0    1
>     2    3    4    5    6
>     7    8
> Sum = 30
> ```

#### 解题思路

#### 提交代码
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
#### 总结

难度1.5星

----

### 7-15 计算圆周率(15分)<span style="color:red;">[√]</span>

> 根据下面关系式，求圆周率的值，直到最后一项的值小于给定阈值。
>
> $\frac{\pi}{2}=1+\frac{1}{3}+\frac{2 !}{3 \times 5}+\frac{3 !}{3 \times 5 \times 7}+\cdots+\frac{n !}{3 \times 5 \times 7 \times \cdots \times(2 n+1)}+\cdots$
>
> ### 输入格式：
>
> 输入在一行中给出小于1的阈值。
>
> ### 输出格式：
>
> 在一行中输出满足阈值条件的近似圆周率，输出到小数点后6位。
>
> ### 输入样例：
>
> ```in
> 0.01 
> ```
>    
>    ### 输出样例：
> 
>```out
> 3.132157
>```

#### 解题思路

#### 提交代码
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
#### 总结

难度1.5星

----

### 7-16 求符合给定条件的整数集(15分)<span style="color:red;">[√]</span>

> 给定不超过6的正整数A，考虑从A开始的连续4个数字。请输出所有由它们组成的无重复数字的3位数。
>
> ### 输入格式：
>
> 输入在一行中给出A。
>
> ### 输出格式：
>
> 输出满足条件的的3位数，要求从小到大，每行6个整数。整数间以空格分隔，但行末不能有多余空格。
>
> ### 输入样例：
>
> ```in
> 2 
> ```
>
> ### 输出样例：
>
> ```out
> 234 235 243 245 253 254
> 324 325 342 345 352 354
> 423 425 432 435 452 453
> 523 524 532 534 542 543
> ```

#### 解题思路

#### 提交代码
```c
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
#### 总结

难度1.5星

----

### 7-17 爬动的蠕虫(15分)<span style="color:red;">[√]</span>

> 一条蠕虫长1寸，在一口深为N寸的井的底部。已知蠕虫每1分钟可以向上爬U寸，但必须休息1分钟才能接着往上爬。在休息的过程中，蠕虫又下滑了D寸。就这样，上爬和下滑重复进行。请问，蠕虫需要多长时间才能爬出井？
>
> 这里要求不足1分钟按1分钟计，并且假定只要在某次上爬过程中蠕虫的头部到达了井的顶部，那么蠕虫就完成任务了。初始时，蠕虫是趴在井底的（即高度为0）。
>
> ### 输入格式：
>
> 输入在一行中顺序给出3个正整数N、U、D，其中D<U，N不超过100。
>
> ### 输出格式：
>
> 在一行中输出蠕虫爬出井的时间，以分钟为单位。
>
> ### 输入样例：
>
> ```in
> 12 3 1  
> ```
>
> ### 输出样例：
>
> ```out
> 11
> ```

#### 解题思路

#### 提交代码
```c
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
#### 总结

难度1.5星

----

### 7-18<<span style="color:red;">递归</span>>二分法求多项式单根 (20分)

> 二分法求函数根的原理为：如果连续函数*f*(*x*)在区间[*a*,*b*]的两个端点取值异号，即$f(a) f(b)<0$，则它在这个区间内至少存在1个根$r$，即$f(r)=0$。
>
> 二分法的步骤为：
>
> - 检查区间长度，如果小于给定阈值，则停止，输出区间中点$(a+b) / 2$；否则
> - 如果$f(a) f(b)<0$，则计算中点的值$f((a+b) / 2)$；
> - 如果$f((a+b) / 2)$正好为0，则(*a*+*b*)/2就是要求的根；否则
> - 如果$f((a+b) / 2)$与*f*(*a*)同号，则说明根在区间$[(a+b) / 2, b]$，令$a=(a+b) / 2$，重复循环；
> - 如果$f((a+b) / 2)$与*f*(*b*)同号，则说明根在区间$[a,(a+b)/2]$，令$b=(a+b) / 2$，重复循环。
>
> 本题目要求编写程序，计算给定3阶多项式$f(x)=a_{3} x^{3}+a_{2} x^{2}+a_{1} x+a_{0}$在给定区间$[a,b]$内的根。
>
> ### 输入格式：
>
> 输入在第1行中顺序给出多项式的4个系数$a3、a2、a1、a0$，在第2行中顺序给出区间端点$a$和$b$。题目保证多项式在给定区间内存在唯一单根。
>
> ### 输出格式：
>
> 在一行中输出该多项式在该区间内的根，精确到小数点后2位。
>
> ### 输入样例：
>
> ```in
> 3 -1 -3 1
> -0.5 0.5    
> ```
>
> ### 输出样例：
>
> ```out
> 0.33
> ```

#### 解题思路

#### 提交代码
```c
#include <stdio.h>
#include <math.h>
double a3, a2, a1, a0;

double f(double a);
double getRoot(double a,double b);

int main()
{
    double a,b;
    scanf("%lf%lf%lf%lf",&a3,&a2,&a1,&a0);
    scanf("%lf%lf",&a,&b);
    double root=getRoot(a,b);
    printf("%.2f\n",root);

    return 0;
}

double f(double a)
{
    return a3*pow(a,3)+a2*pow(a,2)+a1*a+a0;
}
double getRoot(double a,double b)
{
    while((b-a)>0.001)
    {
        if(f((a+b)/2)==0)
        {
            return (a+b)/2;
        }
        else if(f((a+b)/2)*f(a)>0)
        {
            a=(a+b)/2;
        }
        else
        {
            b=(a+b)/2;
        }
    }
        return (a+b)/2;
}

```
#### 总结

难度1星

----

### 7-19<<span style="color:red;">暴力求解</span>>支票面额 (15分)<span style="color:red;">[√]</span>

> 一个采购员去银行兑换一张$y$元$f$分的支票，结果出纳员错给了$f$元$y$分。采购员用去了$n$分之后才发觉有错，于是清点了余额尚有$2y$元$2f$分，问该支票面额是多少？
>
> ### 输入格式：
>
> 输入在一行中给出小于100的正整数$n$。
>
> ### 输出格式：
>
> 在一行中按格式`y.f`输出该支票的原始面额。如果无解，则输出`No Solution`。
>
> 
>
> ### 输入样例1：
>
> ```in
> 23    
> ```
>
> ### 输出样例1：
>
> ```out
> 25.51 
> ```
>
> ### 输入样例2：
>
> ```
> 22   
> ```
>
> ### 输出样例2：
>
> ```
> No Solution
> ```

#### 解题思路

#### 提交代码
```c
#include <stdio.h>

int main(){
	int n,f,y;
	int count=0;
	
	scanf("%d",&n);
	
	for(y=0;y<100;y++){
  		for(f=0;f<100;f++){
			if(98*f-199*y-n==0){
				count=1;
				printf("%d.%d", y, f);
			}
		}
	}
	if(count==0)
		printf("No Solution");
	return 0;
}
```
#### 总结

难度1.5星

----

### 7-20 <<span style="color:red;">暴力求解</span>>打印九九口诀表 (15分)<span style="color:red;">[√]</span>

> 下面是一个完整的下三角九九口诀表：
>
> ```out
> 1*1=1   
> 1*2=2   2*2=4   
> 1*3=3   2*3=6   3*3=9   
> 1*4=4   2*4=8   3*4=12  4*4=16  
> 1*5=5   2*5=10  3*5=15  4*5=20  5*5=25  
> 1*6=6   2*6=12  3*6=18  4*6=24  5*6=30  6*6=36  
> 1*7=7   2*7=14  3*7=21  4*7=28  5*7=35  6*7=42  7*7=49  
> 1*8=8   2*8=16  3*8=24  4*8=32  5*8=40  6*8=48  7*8=56  8*8=64  
> 1*9=9   2*9=18  3*9=27  4*9=36  5*9=45  6*9=54  7*9=63  8*9=72  9*9=81  
> ```
>
> 本题要求对任意给定的一位正整数`N`，输出从`1*1`到`N*N`的部分口诀表。
>
> ### 输入格式：
>
> 输入在一行中给出一个正整数`N`（1≤`N`≤9）。
>
> ### 输出格式：
>
> 输出下三角`N*N`部分口诀表，其中等号右边数字占4位、左对齐。
>
> ### 输入样例：
>
> ```in
> 4   
> ```
>
> ### 输出样例：
>
> ```out
> 1*1=1   
> 1*2=2   2*2=4   
> 1*3=3   2*3=6   3*3=9   
> 1*4=4   2*4=8   3*4=12  4*4=16  
> ```

#### 解题思路

#### 提交代码
```c
#include <stdio.h>

int main(){
	int n;
	
	scanf("%d",&n);
	
	for(int i=1;i<=n;i++){
		for(int j=1;j<=i;j++){
			printf("%d*%d=%-4d",j,i,i*j);
		}
		printf("\n");
	}
	
	return 0;
}


```
#### 总结

难度1.5星

----

### 7-21 <<span style="color:red;">暴力求解</span>>求特殊方程的正整数解 (15分)<span style="color:red;">[√]</span>

> 本题要求对任意给定的正整数$N$，求方程$X^{2}+Y^{2}=N$的全部正整数解。
>
> ### 输入格式：
>
> 输入在一行中给出正整数$N$（≤10000）。
>
> ### 输出格式：
>
> 输出方程$X^{2}+Y^{2}=N$的全部正整数解，其中$X \leq Y$。每组解占1行，两数字间以1空格分隔，按$X$的递增顺序输出。如果没有解，则输出`No Solution`。
>
> ### 输入样例1：
>
> ```in
> 884    
> ```
>
> ### 输出样例1：
>
> ```out
> 10 28
> 20 22  
> ```
>
> ### 输入样例2：
>
> ```
> 11    
> ```
>
> ### 输出样例2：
>
> ```
> No Solution
> ```

#### 解题思路

#### 提交代码
```c
#include <stdio.h>

int main(){
	int x,y,n;
	int count=0;
	scanf("%d",&n);
	
	for(x=1;x<=n;x++){
		for(y=x;y<=n;y++){
			
			if((x*x+y*y)==n){
				printf("%d %d\n",x,y);
				count=1;
			}
			
		}
	}
	
	if(count==0){
		printf("No Solution");
	}
	
	return 0;
}

```
#### 总结

难度1.5星

----

### 7-22 <<span style="color:red;">函数</span>>龟兔赛跑 (20分)<span style="color:red;">[√]</span>

> 乌龟与兔子进行赛跑，跑场是一个矩型跑道，跑道边可以随地进行休息。乌龟每分钟可以前进3米，兔子每分钟前进9米；兔子嫌乌龟跑得慢，觉得肯定能跑赢乌龟，于是，每跑10分钟回头看一下乌龟，若发现自己超过乌龟，就在路边休息，每次休息30分钟，否则继续跑10分钟；而乌龟非常努力，一直跑，不休息。假定乌龟与兔子在同一起点同一时刻开始起跑，请问T分钟后乌龟和兔子谁跑得快？
>
> ### 输入格式：
>
> 输入在一行中给出比赛时间T（分钟）。
>
> ### 输出格式：
>
> 在一行中输出比赛的结果：乌龟赢输出`@_@`，兔子赢输出`^_^`，平局则输出`-_-`；后跟1空格，再输出胜利者跑完的距离。
>
> ### 输入样例：
>
> ```in
> 242
> ```
>
> ### 输出样例：
>
> ```out
> @_@ 726
> ```

#### 解题思路

#### 提交代码
```c
#include <stdio.h>

int main(){
	int x=0,y=0,t=1,n;
	int rest=0;
	
	scanf("%d",&n);
	do{
		x=3*t;
		y=9*(t-rest*30);
		if(t%10==0&& y>x && t!=0){//回头 
			t+=30;
			if(t>n){
				x=3*n;
				break;
			}	
			rest++;
		}else{
			t++;
		}
	}while(t<=n);
	if(x>y)
		printf("@_@ %d",x);
	else if(x<y)
		printf("^_^ %d",y);
	else
		printf("-_- %d",y);
	
	
	return 0;
}
```
#### 总结

难度2星

----

### 7-23 币值转换 (20分)

> 输入一个整数（位数不超过9位）代表一个人民币值（单位为元），请转换成财务要求的大写中文格式。如23108元，转换后变成“贰万叁仟壹百零捌”元。为了简化输出，用小写英文字母a-j顺序代表大写数字0-9，用S、B、Q、W、Y分别代表拾、百、仟、万、亿。于是23108元应被转换输出为“cWdQbBai”元。
>
> ### 输入格式：
>
> 输入在一行中给出一个不超过9位的非负整数。
>
> ### 输出格式：
>
> 在一行中输出转换后的结果。注意“零”的用法必须符合中文习惯。
>
> ### 输入样例1：
>
> ```in
> 813227345  
> ```
>
> ### 输出样例1：
>
> ```out
> iYbQdBcScWhQdBeSf  
> ```
>
> ### 输入样例2：
>
> ```in
> 6900
> ```
>
> ### 输出样例2：
>
> ```out
> gQjB
> ```

#### 解题思路

https://blog.csdn.net/yubai258/article/details/81362774

#### 提交代码
```
#include<stdio.h>
#include<string.h>
int main()
{
char a[10]={'a','b','c','d','e','f','g','h','i','j'};
char b[]={' ',' ','S','B','Q','W','S','B','Q','Y'};
char num[10];
gets(num);
int l=strlen(num);
int n;
int i=0;
int ling=0;
int k=0;
if(num[0]=='0'&&l==1) printf("a");//0的情况，但测试点不包含这个
else
while(l-->0)
{
n=num[i++]-'0';
if(n!=0)
{
if(ling==1)
printf("a");
printf("%c",a[n]);
ling=0;
}
else
{
ling=1;
if(l==4&&k==1) printf("W");
continue;
}//按照中文习惯，四位数一段规律，再考虑万怎么处理
if(l>0)
{
if(l>4&&l<8) k=1;
printf("%c",b[l+1]);
}
}
return 0;
}
```
#### 总结

难度2星

----
### 7-24 约分最简分式 (15分)<span style="color:red;">[√]</span>

> 分数可以表示为`分子/分母`的形式。编写一个程序，要求用户输入一个分数，然后将其约分为最简分式。最简分式是指分子和分母不具有可以约分的成分了。如6/12可以被约分为1/2。当分子大于分母时，不需要表达为整数又分数的形式，即11/8还是11/8；而当分子分母相等时，仍然表达为1/1的分数形式。
>
> ### 输入格式：
>
> 输入在一行中给出一个分数，分子和分母中间以斜杠`/`分隔，如：`12/34`表示34分之12。分子和分母都是正整数（不包含0，如果不清楚正整数的定义的话）。
>
> **提示：**在`scanf`的格式字符串中加入`/`，让`scanf`来处理这个斜杠。
>
> ### 输出格式：
>
> 在一行中输出这个分数对应的最简分式，格式与输入的相同，即采用`分子/分母`的形式表示分数。如 `5/6`表示6分之5。
>
> ### 输入样例：
>
> ```in
> 66/120 
> ```
>
> ### 输出样例：
>
> ```out
> 11/20
> ```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>
int main(){
	int a,b;
	scanf("%d/%d",&a,&b);
	for(int i=1;i<=b;i++){
		for(int j=1;j<=b;j++){
			if( a%j==0 && b%j==0){
				a/=j;
				b/=j;
			}
		}
	}
	printf("%d/%d",a,b);
	return 0;
} 
```

#### 总结

难度2星

----
### 7-25 念数字 (15分)<span style="color:red;">[√]</span>

> 输入一个整数，输出每个数字对应的拼音。当整数为负数时，先输出`fu`字。十个数字对应的拼音如下：
>
> ```
> 0: ling
> 1: yi
> 2: er
> 3: san
> 4: si
> 5: wu
> 6: liu
> 7: qi
> 8: ba
> 9: jiu    
> ```
>
> ### 输入格式：
>
> 输入在一行中给出一个整数，如：`1234`。
>
> **提示：整数包括负数、零和正数。**
>
> ### 输出格式：
>
> 在一行中输出这个整数对应的拼音，每个数字的拼音之间用空格分开，行末没有最后的空格。如 `yi er san si`。
>
> ### 输入样例：
>
> ```in
> -600   
> ```
>
> ### 输出样例：
>
> ```out
> fu liu ling ling
> ```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>
void fomatnum(int num);
int main(){
	int i=0,j=0,num,count=0;
	int ch[100];
	scanf("%d",&num);
	if(num==0)printf("ling");
	if(num<0){
		printf("fu ");
		num=-num;
	}
	while(num!=0){
        ch[count]=num%10;
        num/=10;
        count++;
    }
	for(j=count-1;j>=0;j--){
		fomatnum(ch[j]);
		if(j!=0){
			printf(" ");
		}
	}
	return 0;
} 
void fomatnum(int num){
	switch(num){
		case 0:
			printf("ling");
			break;
		case 1:
			printf("yi");
			break;
		case 2:
			printf("er");
			break;
		case 3:
			printf("san");
			break;
		case 4:
			printf("si");
			break;
		case 5:
			printf("wu");
			break;
		case 6:
			printf("liu");
			break;
		case 7:
			printf("qi");
			break;
		case 8:
			printf("ba");
			break;
		case 9:
			printf("jiu");
			break;
		default:
			break;
	}
} 
```

#### 总结

难度2星

----
### 7-26 单词长度 (15分)

> 你的程序要读入一行文本，其中以空格分隔为若干个单词，以`.`结束。你要输出每个单词的长度。这里的单词与语言无关，可以包括各种符号，比如`it's`算一个单词，长度为4。注意，行中可能出现连续的空格；最后的`.`不计算在内。
>
> ### 输入格式：
>
> 输入在一行中给出一行文本，以`.`结束
>
> **提示：**用`scanf("%c",...);`来读入一个字符，直到读到`.`为止。
>
> ### 输出格式：
>
> 在一行中输出这行文本对应的单词的长度，每个长度之间以空格隔开，行末没有最后的空格。
>
> ### 输入样例：
>
> ```in
> It's great to see you here.
> ```
>    
>    ### 输出样例：
> 
>```out
> 4 5 2 3 3 4
>```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>


int main()
{	int count=0;
	char a;
	int flag=1;
	do{
		scanf("%c",&a);
		if(a==' '&& count!=0){
			if(flag!=1){
				printf(" ");
			}
			printf("%d",count);
			count=0;
			flag=0;		
		}else if(a=='.'&& count!=0){
			if(flag!=1){
				printf(" ");
			}
			printf("%d",count);
			count=0;
			flag=0;
		}else if(count==0&&a==' '){
		}else
			count++;
	}while(a!='.');
  	return 0;   
}


```

#### 总结

难度2星

----
### 7-27 冒泡法排序 (20分)<span style="color:red;">[√]</span>

> 将*N*个整数按从小到大排序的冒泡排序法是这样工作的：从头到尾比较相邻两个元素，如果前面的元素大于其紧随的后面元素，则交换它们。通过一遍扫描，则最后一个元素必定是最大的元素。然后用同样的方法对前$N−1$个元素进行第二遍扫描。依此类推，最后只需处理两个元素，就完成了对$N$个数的排序。
>
> 本题要求对任意给定的$K（<N）$，输出扫描完第*K*遍后的中间结果数列。
>
> ### 输入格式：
>
> 输入在第1行中给出$N$和$K（1≤K<N≤100）$，在第2行中给出$N$个待排序的整数，数字间以空格分隔。
>
> ### 输出格式：
>
> 在一行中输出冒泡排序法扫描完第*K*遍后的中间结果数列，数字间以空格分隔，但末尾不得有多余空格。
>
> ### 输入样例：
>
> ```in
> 6 2
> 2 3 5 1 6 4   
> ```
>
> ### 输出样例：
>
> ```out
> 2 1 3 4 5 6
> ```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>

int main()
{	
	int N,K;
	
	scanf("%d %d",&N,&K);
	int nums[N];
	for(int i=0;i<N;i++){
		scanf("%d",&nums[i]);
	}
	for(int i=0;i<K;i++){
		for(int j=0;j<N-1;j++){
			int t=nums[j];
			if(nums[j]>nums[j+1]){
				nums[j]=nums[j+1];
				nums[j+1]=t;
			}			
		}		
	}
	for(int i=0;i<N;i++){
		if(i!=0){
			printf(" ");
		}
		printf("%d",nums[i]);
	}
  	return 0;   
}
```

#### 总结

难度2星

----

### 7-28 猴子选大王 (20分)<span style="color:red;">[√]</span>

> 一群猴子要选新猴王。新猴王的选择方法是：让N只候选猴子围成一圈，从某位置起顺序编号为1~N号。从第1号开始报数，每轮从1报到3，凡报到3的猴子即退出圈子，接着又从紧邻的下一只猴子开始同样的报数。如此不断循环，最后剩下的一只猴子就选为猴王。请问是原来第几号猴子当选猴王？
>
> ### 输入格式：
>
> 输入在一行中给一个正整数N（≤1000）。
>
> ### 输出格式：
>
> 在一行中输出当选猴王的编号。
>
> ### 输入样例：
>
> ```in
> 11   
> ```
>
> ### 输出样例：
>
> ```out
> 7
> ```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>

#define NUM 3


int main()
{
	int N;	
	scanf("%d",&N);
	
	int monkeys[N];
	for(int i=0;i<N;i++){
		monkeys[i]=i+1;
	}
	int count=1;//计数器 
	int index=0;
	int num=N; 
	do{
		if(monkeys[index]!=0&&count==NUM){//当猴子存在且报数3，将其删除 
			monkeys[index]=0;
			count=1;
			index++;
			num--;
		}else if(monkeys[index]!=0&&count!=NUM){//当猴子存在，报数不到， 
			index++;
			count++;
		}else{//当猴子不存在
			index++;
		}
		
		if(index==N){
			index=0;
		}
		
		
	}while(num!=1);
	
	for(int i=0;i<N;i++){//输出王 
		if(monkeys[i]!=0){
			printf("%d",monkeys[i]);
		}
	}
  	return 0;   
}
```

#### 总结

难度2星

----

### 7-29 删除字符串中的子串 (20分)<span style="color:red;">[√]</span>

> 输入2个字符串S1和S2，要求删除字符串S1中出现的所有子串S2，即结果字符串中不能包含S2。
>
> ### 输入格式：
>
> 输入在2行中分别给出不超过80个字符长度的、以回车结束的2个非空字符串，对应S1和S2。
>
> ### 输出格式：
>
> 在一行中输出删除字符串S1中出现的所有子串S2后的结果字符串。
>
> ### 输入样例：
>
> ```in
> Tomcat is a male ccatat
> cat   
> ```
>
> ### 输出样例：
>
> ```out
> Tom is a male 
> ```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>
#include <string.h>

int main()
{
	char s1[81];
    char s2[81];
    char t[81];/*定义临时数组,因为strcpy, strcat 中的传入参数的内存地址不能重叠*/
    char *p;/*定义指针p，来接收匹配成功返回的地址*/
    gets(s1);
    gets(s2);
    while((p=strstr(s1,s2))!=NULL)/*找到s2在s1中第一次出现的首个字符位置，如果合法*/
    {
    	strcpy(t,p+strlen(s2));/*先将p所指位置偏移s2长度之后的所有字符拷贝到临时数组中*/
    	*p='\0';/*将p的内容置为结束符*/
    	strcat(s1,t);/*将t的内容接到s1末尾，这里是接在结束符之后，同时也会覆盖原结束符之后的字符，这样便完成了一次删除*/
    }
    puts(s1);
    return 0;
}
```

#### 总结

难度2星

----

### 7-30 字符串的冒泡排序 (20分)

> 我们已经知道了将$N$个整数按从小到大排序的冒泡排序法。本题要求将此方法用于字符串序列，并对任意给定的$K(<N)$，输出扫描完第$K$遍后的中间结果序列。
>
> ### 输入格式：
>
> 输入在第1行中给出$N$和$K(1 \leq K<N \leq 100)$，此后$N$行，每行包含一个长度不超过10的、仅由小写英文字母组成的非空字符串。
>
> ### 输出格式：
>
> 输出冒泡排序法扫描完第$K$遍后的中间结果序列，每行包含一个字符串。
>
> ### 输入样例：
>
> ```in
> 6 2
> best
> cat
> east
> a
> free
> day  
> ```
>
> ### 输出样例：
>
> ```out
> best
> a
> cat
> day
> east
> free
> ```

#### 解题思路

#### 提交代码

```
#include <stdio.h>
#include <string.h>

int main()
{	
	int N,K;
	
	scanf("%d %d",&N,&K);
	char s[N][80];
	
	for(int i=0;i<N;i++){
		scanf("%s",s[i]);
	}
	
	for(int i=0;i<K;i++){
		for(int j=0;j<N-1;j++){
			char t[80];

			if(strcmp(s[j],s[j+1])>0){
				strcpy(t,s[j]);
				strcpy(s[j],s[j+1]);
				strcpy(s[j+1],t);
			}			
		}		
	}
	
	
	for(int i=0;i<N;i++){
		if(i!=0){
			printf("\n");
		}
		printf("%s",s[i]);
	}
	
  	return 0;   
}
```

#### 总结

难度2星

----

### 7-31 字符串循环左移 (20分)

> 输入一个字符串和一个非负整数$N$，要求将字符串循环左移$N$次。
>
> ### 输入格式：
>
> 输入在第1行中给出一个不超过100个字符长度的、以回车结束的非空字符串；第2行给出非负整数$N$。
>
> ### 输出格式：
>
> 在一行中输出循环左移$N$次后的字符串。
>
> ### 输入样例：
>
> ```in
> Hello World!
> 2  
> ```
>
> ### 输出样例：
>
> ```out
> llo World!He
> ```

#### 解题思路

#### 提交代码

```c
#include <stdio.h>
#include <string.h>

int main()
{	
	int N;
	char s;
	char str[100];
	int count=0;
	
	while((s=getchar()) != '\n'){
		str[count]=s;
		count++;
	}
	scanf("%d",&N);
	for(int i=0;i<N;i++){
		char t=str[0];
		for(int j=0;j<count;j++){
			str[j]=str[j+1];
		}
		str[count-1]=t;
	}
	
	for(int i=0;i<count;i++){
		printf("%c",str[i]);
	}
	
	
  	return 0;   
}


```
#### 总结

难度2星

----

### 7-32 说反话-加强版 (20分)

> 给定一句英语，要求你编写程序，将句中所有单词的顺序颠倒输出。
>
> ### 输入格式：
>
> 测试输入包含一个测试用例，在一行内给出总长度不超过500 000的字符串。字符串由若干单词和若干空格组成，其中单词是由英文字母（大小写有区分）组成的字符串，单词之间用若干个空格分开。
>
> ### 输出格式：
>
> 每个测试用例的输出占一行，输出倒序后的句子，并且保证单词间只有1个空格。
>
> ### 输入样例：
>
> ```in
> Hello World   Here I Come   
> ```
>
> ### 输出样例：
>
> ```out
> Come I Here World Hello
> ```

#### 解题思路

https://www.cnblogs.com/lingr7/p/9432803.html

#### 提交代码

```c
#include<stdio.h>//标准c，没有用c++的string，这样首先读取字符串就是个问题了 
#define MAX 500000
//先处理字符串，删除多余的空格，形成新字符串 
//Hello World   Here I Come
int main ()
{
    char s;//指单独一个字符 
    char t[MAX];//创建一个字符数组 
    int i = 0, count = 0, flag = 0;
    while ((s=getchar()) != '\n') {//getchar每次从标准输入读入一个字符 ，标准输入会有'\n'??? 
        if (s != ' ') {
            flag = 1; //标记遇到单词 
            t[i++] = s;
            count = 0;
        } else if (count > 0) {
            continue;//contiue跳过
        } else if (flag) {
            t[i++] = s; //只有之前遇到单词的情况下碰到空格才把这个空格写入目标字符串 
            count ++;//这里换成count=1也是完全一样 
        }
    } //删除多余的空格，将目标字符串放入 t 中 
    //这里的count起了什么作用呢？ 
    //如遇到 Hello,都存入t中，遇到第一个空格，此时count=0,flag=1，把空格存入t,count=1
    //World后面的空格 ,第二个空格，遇到空格继续读下一个字符即，continue,起一个跳过作用 
    //开头就是空格咋办？啥也不操作 
    
    
    count = 0;
    int j;
    for (i-=1; i>=0; i--) {//i-=1.i=i-1,最后一个标号为i里面是没存东西的 
        if (t[i] != ' ') {
            count ++; // 这里的 count 统计的是一个单词里字母的个数 
        } else if (t[i]==' ' && count > 0) {
            for (j=i+1; j<=i+count; j++) {
                printf("%c", t[j]);
            } //遇到空格就输出单词 
            printf(" ");
            count = 0;
        }
    } // 还剩最后一个单词没输出，因为最后一个单词可能前方无空格 ，只完成了count++，但是没有遇到 空格，那么逻辑是一样的 
    for (j=i+1; j<=i+count; j++) {
        printf("%c", t[j]);
    } //i,j的变量作用范围非常的有用
    //这么看来字符数组其实非常的方便，不必非要使用c++的string类 ，continue用来跳过也是极好的 

    return 0; 
}
```

#### 总结

难度2星

----
### 7-33 有理数加法 (15分)

> 本题要求编写程序，计算两个有理数的和。
>
> ### 输入格式：
>
> 输入在一行中按照`a1/b1 a2/b2`的格式给出两个分数形式的有理数，其中分子和分母全是整形范围内的正整数。
>
> ### 输出格式：
>
> 在一行中按照`a/b`的格式输出两个有理数的和。注意必须是该有理数的最简分数形式，若分母为1，则只输出分子。
>
> ### 输入样例1：
>
> ```in
> 1/3 1/6  
> ```
>
> ### 输出样例1：
>
> ```out
> 1/2 
> ```
>
> ### 输入样例2：
>
> ```
> 4/3 2/3   
> ```
>
> ### 输出样例2：
>
> ```
> 2
> ```

#### 解题思路

#### 提交代码

```c
#include<stdio.h>
#include<stdlib.h>

int main(){
	int a1,a2,b1,b2;
    scanf("%d/%d %d/%d",&a1,&a2,&b1,&b2);
    a1=a1*b2;
    b1=b1*a2;
    a2=a2*b2;
    b2=a2;
    int mol=a1+b1;
    int denom=a2;
    
    if(mol>=denom){
    	for(int i=1;i<=mol;i++){
    		if(mol%i==0&&denom%i==0){
    			mol/=i;
    			denom/=i;
    			i=1;
			}
		}
		if(denom==1){
			printf("%d",mol);
		}else{
			printf("%d/%d",mol,denom);
		}
	}else{
		for(int i=1;i<=denom;i++){
    		if(mol%i==0&&denom%i==0){
    			mol/=i;
    			denom/=i;
    			i=1;
			}
		}
		if(denom==1){
			printf("%d",mol);
		}else{
			printf("%d/%d",mol,denom);
		}
	}
    return 0; 
} 
```

#### 总结

难度2星

----
### 7-34 通讯录的录入与显示 (10分)

> 通讯录中的一条记录包含下述基本信息：朋友的姓名、出生日期、性别、固定电话号码、移动电话号码。 本题要求编写程序，录入$N$条记录，并且根据要求显示任意某条记录。
>
> ### 输入格式：
>
> 输入在第一行给出正整数$N(\leq 10)$；随后$N$行，每行按照格式`姓名 生日 性别 固话 手机`给出一条记录。其中`姓名`是不超过10个字符、不包含空格的非空字符串；生日按`yyyy/mm/dd`的格式给出年月日；性别用`M`表示“男”、`F`表示“女”；`固话`和`手机`均为不超过15位的连续数字，前面有可能出现`+`。
>
> 在通讯录记录输入完成后，最后一行给出正整数$K$，并且随后给出$K$个整数，表示要查询的记录编号（从$0$到$N−1$顺序编号）。数字间以空格分隔。
>
> ### 输出格式：
>
> 对每一条要查询的记录编号，在一行中按照`姓名 固话 手机 性别 生日`的格式输出该记录。若要查询的记录不存在，则输出`Not Found`。
>
> ### 输入样例：
>
> ```in
> 3
> Chris 1984/03/10 F +86181779452 13707010007
> LaoLao 1967/11/30 F 057187951100 +8618618623333
> QiaoLin 1980/01/01 M 84172333 10086
> 2 1 7   
> ```
>
> ### 输出样例：
>
> ```out
> LaoLao 057187951100 +8618618623333 F 1967/11/30
> Not Found
> ```

#### 解题思路

#### 提交代码

```c
#include<stdio.h>
#include<stdlib.h>
typedef struct Person{
    char name[20];
    char birthday[20];
    char gender[10];
    char tel[20];
    char mobile[20];
}Person1;

int main(){
    int n,i,a,b[20];
    scanf("%d",&n);
    Person1 p[20];
    for(i=0;i<n;i++){
        scanf("%s %s %s %s %s",p[i].name,p[i].birthday,p[i].gender,p[i].tel,p[i].mobile);
    }
    scanf("%d",&a);
    for(i=0;i<a;i++){
        scanf("%d",&b[i]); 
    }
    for(i=0;i<a;i++){
        if(b[i]>=0 && b[i]<n){
            printf("%s %s %s %s %s\n",p[b[i]].name,p[b[i]].tel,p[b[i]].mobile,p[b[i]].gender,p[b[i]].birthday);
        }else{
            printf("Not Found\n");
        }
    }

} 

```

#### 总结

难度2星

----
### 7-35 有理数均值 (20分)

> 本题要求编写程序，计算N个有理数的平均值。
>
> ### 输入格式：
>
> 输入第一行给出正整数N（≤100）；第二行中按照`a1/b1 a2/b2 …`的格式给出N个分数形式的有理数，其中分子和分母全是整形范围内的整数；如果是负数，则负号一定出现在最前面。
>
> ### 输出格式：
>
> 在一行中按照`a/b`的格式输出N个有理数的平均值。注意必须是该有理数的最简分数形式，若分母为1，则只输出分子。
>
> ### 输入样例1：
>
> ```in
> 4
> 1/2 1/6 3/6 -5/10 
> ```
>
> ### 输出样例1：
>
> ```out
> 1/6   
> ```
>
> ### 输入样例2：
>
> ```
> 2
> 4/3 2/3  
> ```
>
> ### 输出样例2：
>
> ```
> 1
> ```

#### 解题思路

#### 提交代码

```c
#include<stdio.h>

int gcd(int a,int b); 
typedef struct Nums{
    int mol; //分子 
    int denom; //分母 
}type;



int main(){
	int a,r,sum1,sum2;
	scanf("%d",&a);
	type n[a];
	
	for(int i=0;i<a;i++){
		scanf("%d/%d",&n[i].mol,&n[i].denom);
	}
	if(a==1){
		if(n[0].denom==1){
			printf("%d",n[0].mol);
		}else{
			r=gcd(n[0].mol,n[0].denom);
            n[0].mol/=r;
            n[0].denom/=r;
            printf("%d/%d",n[0].mol,n[0].denom);
		}
	}else{
		sum1=n[0].mol; //分子和 
        sum2=n[0].denom; //分母和 
        for(int i=1;i<a;i++){
            sum1=sum1*n[i].denom+sum2*n[i].mol;
            sum2=sum2*n[i].denom; 
            r=gcd(sum1,sum2);
            sum1/=r;
            sum2/=r;
        }
        sum2=sum2*a;
        r=gcd(sum1,sum2);

        sum1/=r;
        sum2/=r;

        if(sum1%sum2==0){
            printf("%d",sum1/sum2);
        }
        else{
            printf("%d/%d",sum1,sum2);
        }
	}
    return 0;
} 

int gcd(int a,int b){//辗转相除法，求最大公约数 

    if(b==0){
        return 1;
    }
    int r=a%b;
    while(r!=0){
        a=b;
        b=r;
        r=a%b;
    }
    return b;
}
```

#### 总结

难度2星

----
### 7-36 复数四则运算 (15分)

> 本题要求编写程序，计算2个复数的和、差、积、商。
>
> ### 输入格式：
>
> 输入在一行中按照`a1 b1 a2 b2`的格式给出2个复数C1=`a1+b1i`和C2=`a2+b2i`的实部和虚部。题目保证C2不为0。
>
> ### 输出格式：
>
> 分别在4行中按照`(a1+b1i) 运算符 (a2+b2i) = 结果`的格式顺序输出2个复数的和、差、积、商，数字精确到小数点后1位。如果结果的实部或者虚部为0，则不输出。如果结果为0，则输出0.0。
>
> ### 输入样例1：
>
> ```in
> 2 3.08 -2.04 5.06
> ```
>
> ### 输出样例1：
>
> ```out
> (2.0+3.1i) + (-2.0+5.1i) = 8.1i
> (2.0+3.1i) - (-2.0+5.1i) = 4.0-2.0i
> (2.0+3.1i) * (-2.0+5.1i) = -19.7+3.8i
> (2.0+3.1i) / (-2.0+5.1i) = 0.4-0.6i   
> ```
>
> ### 输入样例2：
>
> ```
> 1 1 -1 -1.01 
> ```
>
> ### 输出样例2：
>
> ```
> (1.0+1.0i) + (-1.0-1.0i) = 0.0
> (1.0+1.0i) - (-1.0-1.0i) = 2.0+2.0i
> (1.0+1.0i) * (-1.0-1.0i) = -2.0i
> (1.0+1.0i) / (-1.0-1.0i) = -1.0
> ```

#### 解题思路

#### 提交代码

```c
#include<stdio.h>
#include<math.h>
void dayin(double a1,double a2)
{
if(a2<0) printf("(%.1lf%.1lfi)",a1,a2);
else printf("(%.1lf+%.1lfi)",a1,a2);
}
void dayinj(double c1,double c2)
{
if(c2<=0.05&&c2>=-0.05)
printf("%.1lf",c1);
else if(c1<=0.05&&c1>=-0.05)
printf("%.1lfi",c2);
else if(c2<0) printf("%.1lf%.1lfi",c1,c2);
else printf("%.1lf+%.1lfi",c1,c2);
printf("\n");
}
int main()
{
double a1,a2,b1,b2;
scanf("%lf%lf%lf%lf",&a1,&a2,&b1,&b2);
double c1,c2;

c1=a1+b1; c2=a2+b2;
dayin(a1,a2);
printf(" + ");
dayin(b1,b2);
printf(" = ");
dayinj(c1,c2);

c1=a1-b1; c2=a2-b2;
dayin(a1,a2);
printf(" - ");
dayin(b1,b2);
printf(" = ");
dayinj(c1,c2);

c1=a1*b1-a2*b2; c2=a1*b2+a2*b1;
dayin(a1,a2);
printf(" * ");
dayin(b1,b2);
printf(" = ");
dayinj(c1,c2);

c1=(a1*b1+a2*b2)/(b1*b1+b2*b2); c2=(a2*b1-a1*b2)/(b1*b1+b2*b2);
dayin(a1,a2);
printf(" / ");
dayin(b1,b2);
printf(" = ");
dayinj(c1,c2);
return 0;
}
```

#### 总结

难度2星

----
### 7-37 整数分解为若干项之和 (20分)

> 将一个正整数N分解成几个正整数相加，可以有多种分解方法，例如7=6+1，7=5+2，7=5+1+1，…。编程求出正整数N的所有整数分解式子。
>
> ### 输入格式：
>
> 每个输入包含一个测试用例，即正整数$\mathrm{N}(0<\mathrm{N} \leq 30)$。
>
> ### 输出格式：
>
> 按递增顺序输出N的所有整数分解式子。递增顺序是指：对于两个分解序列$\mathrm{N}_{1}=\left\{n_{1}, n_{2}, \cdots\right\}$和$\mathrm{N}_{2}=\left\{m_{1}, m_{2}, \cdots\right\}$，若存在$i$使得$n_{1}=m_{1}, \cdots, n_{i}=m_{i}$，但是$n_{i+1}<m_{i+1}$,则$N1$序列必定在$N2$序列之前输出。每个式子由小到大相加，式子间用分号隔开，且每输出4个式子后换行。
>
> ### 输入样例：
>
> ```in
> 7  
> ```
>
> ### 输出样例：
>
> ```out
> 7=1+1+1+1+1+1+1;7=1+1+1+1+1+2;7=1+1+1+1+3;7=1+1+1+2+2
> 7=1+1+1+4;7=1+1+2+3;7=1+1+5;7=1+2+2+2
> 7=1+2+4;7=1+3+3;7=1+6;7=2+2+3
> 7=2+5;7=3+4;7=7
> ```

#### 解题思路

#### 提交代码

```c
#include<stdio.h>

int N;

int s[31]; // 存放划分结果，这里用了比较简单地容器，数组，比我想象的要简单 
int top = -1; // 数组指针 
int count = 0; // 统计输出的次数 
int sum = 0; // 拆分项累加和 

void division (int i);

int main (){
    scanf ("%d", &N);
    division (1);
    return 0; 
}

void division (int i) {//拆分 
    if (sum == N) {
        count ++;
        printf("%d=", N);
        int k;
        for (k=0; k<top; k++) {
            printf("%d+", s[k]);
        }
        if (count%4 == 0 || s[top] == N) {
            printf("%d\n", s[top]);
        } else {
            printf("%d;", s[top]);
        }
        return;
    } // 输出部分 
    if (sum > N) {
        return;
    }
    for (int j=i; j<=N; j++) { 
        s[++top] = j;
        sum += j; 
        division (j);
        sum -= j;
        top --;
    } // 算法主体 
}
```

#### 总结

难度2星

----
### 7-38 数列求和-加强版 (20分)

> 给定某数字$A(1 \leq A \leq 9)$以及非负整数$N(0 \leq N \leq 100000)$，求数列之和$S=A+A A+A A A+\cdots+A A \cdots A$（$N$个$A$）。例如$A=1$, $N=3$时，$S=1+11+111=123$。
>
> ### 输入格式：
>
> 输入数字$A$与非负整数$N$。
>
> ### 输出格式：
>
> 输出其$N$项数列之和$S$的值。
>
> ### 输入样例：
>
> ```in
> 1 3    
> ```
>
> ### 输出样例：
>
> ```out
> 123
> ```

#### 解题思路

https://blog.csdn.net/omegaaa/article/details/85464327

#### 提交代码

```c
#include <stdio.h>

int main()
{
	int Digit[100003] = {0},Sum[100003] = {0};
	int A, N, Flag, i;
	scanf("%d %d", &A, &N);
	for( i=1; i<=N; i++){
		Digit[i]=A;//将Digit数组中前N个元素赋A值；
	}
	for( i=1; i<=100003; i++){
		Sum[i] += Digit[i] * (N-i+1);
		Sum[i+1] = Sum[i] / 10;
		Sum[i] %= 10;
	}
	for( i=100003; i>=1; i--){
		if(Sum[i] != 0){
			Flag = i;
			break;
		}
	}
	for( i=Flag; i>=1; i--){
		printf("%d",Sum[i]);
	}
	return 0;
}

```

#### 总结

难度2星

----