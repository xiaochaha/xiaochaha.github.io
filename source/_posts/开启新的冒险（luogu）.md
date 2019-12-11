---
title: 开启新的冒险（luogu）
date: 2019-12-10 23:06:39
tags:
- 'Java基础题'
- ‘luogu’
categories: 'JavaSE'

---

## 关卡1-1 洛谷的第一个任务

### P1000 [超级玛丽游戏](https://www.luogu.com.cn/problem/P1000)

```java
public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
System.out.println("                ********\r\n" + 
		"               ************\r\n" + 
		"               ####....#.\r\n" + 
		"             #..###.....##....\r\n" + 
		"             ###.......######              ###            ###\r\n" + 
		"                ...........               #...#          #...#\r\n" + 
		"               ##*#######                 #.#.#          #.#.#\r\n" + 
		"            ####*******######             #.#.#          #.#.#\r\n" + 
		"           ...#***.****.*###....          #...#          #...#\r\n" + 
		"           ....**********##.....           ###            ###\r\n" + 
		"           ....****    *****....\r\n" + 
		"             ####        ####\r\n" + 
		"           ######        ######\r\n" + 
		"##############################################################\r\n" + 
		"#...#......#.##...#......#.##...#......#.##------------------#\r\n" + 
		"###########################################------------------#\r\n" + 
		"#..#....#....##..#....#....##..#....#....#####################\r\n" + 
		"##########################################    #----------#\r\n" + 
		"#.....#......##.....#......##.....#......#    #----------#\r\n" + 
		"##########################################    #----------#\r\n" + 
		"#.#..#....#..##.#..#....#..##.#..#....#..#    #----------#\r\n" + 
		"##########################################    ############");
	}

}
```

### P1001 [A+B Problem](https://www.luogu.com.cn/problem/P1001)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
        Scanner cin=new Scanner(System.in);
        int a = cin.nextInt(), b = cin.nextInt();
        System.out.println(a+b);
    }
}
```

### P1421 [小玉买文具](https://www.luogu.com.cn/problem/P1421)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
        Scanner cin=new Scanner(System.in);
        int a = cin.nextInt(), b = cin.nextInt();
        int num=(int) ((a+b*0.1)/1.9);
        System.out.println(num);
    }
}
```

### P1425 [小鱼的游泳时间](https://www.luogu.com.cn/problem/P1425)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
        Scanner cin=new Scanner(System.in);
        int a = cin.nextInt(), b = cin.nextInt();
        int c = cin.nextInt(), d = cin.nextInt();
        int e=c-a;
        int f=d-b;
        if (f<0) {
			e-=1;
			f+=60;
		}
        System.out.println(e+" "+f);
    }
}
```

## 关卡1-2 顺序与分支

### P1422 [小玉家的电费](https://www.luogu.com.cn/problem/P1422)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
        Scanner cin=new Scanner(System.in);
        int a = cin.nextInt();
        double rate1=0.4463,rate2=0.4663,rate3=0.5663;
        double sum=0;um
		}else if (150<a && a<401) {
			sum=(a-150)*rate2+150*rate1;
		}else if (400<a) {
			sum=(a-400)*rate3+250*rate2+150*rate1;
		}
        System.out.printf("%.1f",sum);
        
    }
}
```
### P1085 [不高兴的津津](https://www.luogu.com.cn/problem/P1085)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
    	Scanner cin=new Scanner(System.in);
    	int[] schoolTime=new int[7];
    	int[] courseTime=new int[7];
    	for (int i = 0; i < 7; i++) {
    		schoolTime[i] = cin.nextInt();
    		courseTime[i]= cin.nextInt();
		}
    	for (int i = 0; i < 7; i++) {
			if (schoolTime[i]+courseTime[i]>8) {
				System.out.println(i+1);
				break;
			}
		}
        
    }
}
//第一种方法两个for时间复杂度高
//所以想了第二种方法
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
    	Scanner cin=new Scanner(System.in);
    	int schoolTime,courseTime;
    	int day=0,dayTime=0,max=0;
    	for (int i = 0; i < 7; i++) {
    		schoolTime = cin.nextInt();
    		courseTime= cin.nextInt();
    		dayTime=schoolTime+courseTime;
    		if (dayTime>8&&dayTime>max) {
				day=i+1;
				max=dayTime;
			}
		}
    	System.out.println(day);
        
    }
}
```

### P1089 [津津的储蓄计划](https://www.luogu.com.cn/problem/P1089)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
    	Scanner cin=new Scanner(System.in);
    	int sum=0,cum=0,all=0;//sum手里的钱，cum存的钱，最后的钱
    	int moneyIn=300,moneyOut=0,mouth=12;//moneyIn月初的钱，moneyOut预计花销，mouth月
    	for (int i = 1; i < 13; i++) {
    		moneyOut=cin.nextInt();
    		sum+=moneyIn;
    		if (sum<moneyOut&&i<mouth) {
				mouth=-(i);
			}else {
				sum=sum-moneyOut;
				if (sum>100) {
					cum+=(sum/100)*100;
					sum=sum-(sum/100)*100;	
				}			
			}
		}
    	if (mouth<0) {
    		System.out.println(mouth);
		}else {
			all=(int) (cum*1.2)+sum;
			System.out.println(all);
		}
    	
        
    }
}
```

### P1909 [买铅笔](https://www.luogu.com.cn/problem/P1909)

```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) throws Exception {
    	Scanner cin=new Scanner(System.in);
    	int num=0,kindnum=0,kindprice=0;
    	num=cin.nextInt();
    	int sum=0,min=10000000;
    	for (int i = 1; i < 4; i++) {
    		kindnum=cin.nextInt();
    		kindprice=cin.nextInt();
    		if (num%kindnum!=0) {
				sum=(num/kindnum+1)*kindprice;
			}else {
				sum=(num/kindnum)*kindprice;
			}
    		if (sum<min) {
    			min=sum;
			}
    	}
    	System.out.println(min);
    		
    	
        
    }
}
```

## 循环！循环！循环！

### P1008 [三连击](https://www.luogu.com.cn/problem/P1008)
```java
//2个集合内所有数相加相乘结果一样，2个集合的内容一样
public class Main {
	public static void main(String args[]) throws Exception {
		int a = 100, b = 100, c = 100;
		do {
			b = a * 2;
			c = a * 3;
			if((a/100+a/10%10+a%10+b/100+b/10%10+b%10+c/100+c/10%10+c%10==1+2+3+4+5+6+7+8+9)&&((a/100)*(a/10%10)*(a%10)*(b/100)*(b/10%10)*(b%10)*(c/100)*(c/10%10)*(c%10)==(1)*(2)*(3)*(4)*(5)*(6)*(7)*(8)*(9))) {
				System.out.println(a + " " + b + " " + c);
			}
			a ++;
		} while (c < 999);

	}
}
```