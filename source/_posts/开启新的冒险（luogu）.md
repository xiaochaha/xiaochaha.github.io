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