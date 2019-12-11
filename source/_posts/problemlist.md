---
title: problemlist
date: 2019-12-03 21:34:14
tags: 
- 'Java基础题'
- ‘校内’
categories: 'JavaSE'
---

http://10.248.61.41:8080/JudgeOnline/problemlist

有些题可能有更优解

### 1000==A+B Problem==

```java
import java.util.Scanner;

public class Main {
	public static void main(String args[]) throws Exception {
		Scanner cin = new Scanner(System.in);
		int a = cin.nextInt(), b = cin.nextInt();
		System.out.println(a + b);
	}

}
```

### 1001==Hello Word！==

```java
public class Main{
	public static void main(String args[]){
		System.out.println("Hello Word!");
	}
}
```

### 1002==整除与取余数==

```java
public class Main {
	public static void main(String[] args) {
		System.out.println("7/2="+7/2);
		System.out.println("7.0/2="+7.0/2);
		System.out.println("7%2="+7%2);
		System.out.println("7.0%2="+7.0%2);
		System.out.println("-7%2="+(-7%2));
		System.out.println("7%-2="+7%-2);
				
	}
}
```

### 1003==判断一个年份是否为闰年==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int year = sc.nextInt();
		if ((year % 4 == 0 && year % 100 != 0)||(year%400==0)) {
			System.out.println("true");
		} else {
			System.out.println("false");
		}
	}
}
```

### 1004==求一个三位数的数字和==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int num = sc.nextInt();
		int a=num/100;
		int b=num%100/10;
		int c=num%100%10;
		System.out.println(a+b+c);
	}
}
```

### 1005==求3个数中的最大与最小值==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int max,min;
		max=min=0;
		int a = sc.nextInt();
		int b = sc.nextInt();
		int c = sc.nextInt();
		if (a>b&&a>c) {
			max=a;
			min=(b>c)?c:b;
		}
		if (b>a&&b>c) {
			max=b;
			min=(a>c)?c:a;
		}
		if (c>b&&c>a) {
			max=c;
			min=(b>a)?a:b;
		}	
		System.out.println("max="+max);
		System.out.println("min="+min);
	}
}

```

### 1006==判断某年某月有多少天==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int day=0;
		int year = sc.nextInt();
		int month = sc.nextInt();
		switch (month) {
		case 1:case 3:case 5:case 7:case 8:case 10:case 12:
			day=31;
			break;
		case 2:
			if ((year % 4 == 0 && year % 100 != 0)||(year%400==0)) {
				day=29;
			}else {
				day=28;
			}
			break;
		case 4:case 6:case 9:case 11:
			day=30;
			break;
		}
		System.out.println(day);
	}
}
```

### 1007==奇数之和==

```java
public class Main {
	public static void main(String[] args) {
		int sum=0;
		for (int i = 1; i < 200; i++) {
			sum+=i;
			i+=1;
		}
		System.out.println(sum);
	}
}
```

### 1008==递归==

```java
public class Main {

	public static void main(String args[]) {
		int a=1;
		int b=1;
		int c;
		int n=1;
		System.out.print(" "+a+" "+b);
		do {
			c=a+b;
			a=b;
			b=c;
			System.out.print(" "+c);
			n++;
		} while (n<=18);
	}
}
/*老方法
public class Main {
	public static void main(String[] args) {
		int [] nums=new int[20];
		nums[0]=1;
		nums[1]=1;
		System.out.print(" "+nums[0]);
		System.out.print(" "+nums[1]);
		int i = 2;
		while (i < nums.length) {
		nums[i]= nums[i-1]+nums[i-2];
		System.out.print(" "+nums[i]);
			i++;
		}		
		
	}
}
*/
```

### 1009==打印99乘法表==

```java
public class Main {
	public static void main(String[] args) {
		int a=0;
		for (int i = 1; i < 10; i++) {
			for (int j = 1; j < i + 1; j++) {
				a = j*i;
				System.out.printf("%2d *%2d=%2d ",i,j,a);
			}
			System.out.print(" ");
			System.out.println();
		}
	}
}

```

### 1010==求最小公倍数与最大公约数==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int a,b,ta,tb,r,lcm;
		a=b=ta=tb=r=lcm=0;
		Scanner sc=new Scanner(System.in);
		a=sc.nextInt();
		b=sc.nextInt();
		ta = a;tb = b;
		while (tb != 0){//辗转相除法
	        r = ta%tb;
	        ta = tb;
	        tb = r;
	    }
		//ta是最大公约数
	    lcm = a/ta*b;//最小公倍数
	    System.out.println(ta+" "+lcm);
	}
}
```

### 1011==求素数==

```java
public class Main {
	public static void main(String args[]) {
		int count = 0;
		int num = 2;
		boolean isPrime;
		while (count < 50) {
			isPrime = true;
			for (int i = 2; i * i <= num; i++) {
				if (num % i == 0) {
					isPrime = false;
					break;
				}
			}
			if (isPrime) {
				count++;
				if (count % 10 == 0) {
					System.out.printf("%3d%n", num);

				} else {
					System.out.printf("%3d ", num);
				}
			}
			num++;
		}
	}
}
```

### 1012==冒泡排序==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int tmp=0;
		int []nums=new int[10];
		Scanner sc=new Scanner(System.in);
		for (int i = 0; i < nums.length; i++) {//输入数组
			nums[i]=sc.nextInt();
		}
		for (int j = 0; j < nums.length-1; j++) {//j次
			for (int k = 0; k < nums.length-j-1; k++) {//依次比较
				if (nums[k]>nums[k+1]) {
					tmp=nums[k+1];
					nums[k+1]=nums[k];
					nums[k]=tmp;
				}
			}
		}
		for (int num:nums) {
			System.out.print(num+" ");
		}
	}
}
```

### 1013==选择排序==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int min=0;
		int []nums=new int[10];
		Scanner sc=new Scanner(System.in);
		for (int i = 0; i < nums.length; i++) {//输入数组
			nums[i]=sc.nextInt();
		}
		for (int j = 0; j < nums.length-1; j++) {//j次
			min=nums[j];
			for (int k = nums.length-1; k>j; k--) {//依次比较
				if (min>nums[k]) {
					min=nums[k];
					nums[k]=nums[j];
					nums[j]=min;
				}
			}
		}
		for (int num:nums) {
			System.out.print(num+" ");
		}
	}
}

```

### 1014==类与对象==

```java
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		Person p1 = new Person();

		Scanner cin = new Scanner(System.in);

		String name = cin.next();

		int age = cin.nextInt();

		String sex = cin.next();

		p1.setName(name);

		p1.setAge(age);

		p1.setSex(sex);

		p1.showMyself();
	}
	
}

class Person {
	String name;
	int age;
	String sex;

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}

	public String getSex() {
		return sex;
	}

	public void setSex(String sex) {
		this.sex = sex;
	}

	public void showMyself() {
		System.out.println("name=" + name + ",age=" + age + ",sex=" + sex);		
	}
	

}
```

### 1015==类的继承==

```java
import java.util.Scanner;

public class Main {
	public static void main(String args[]) throws Exception {
		Scanner cin = new Scanner(System.in);
		String name = cin.next();
		int age = cin.nextInt();
		String sexs = cin.next();
		char sex = sexs.charAt(0);
		Student st = new Student(name, age, sex);
		name = cin.next();
		age = cin.nextInt();
		sexs = cin.next();
		sex = sexs.charAt(0);
		Teacher th = new Teacher(name, age, sex);
		st.showMyself();
		th.showMyself();

	}
}

class Person {
	String name;
	int age;
	char sex;

	public Person() {
	}
	
	public Person(String name, int age, char sex) {
		this.name = name;
		this.age = age;
		this.sex = sex;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}

	public char getSex() {
		return sex;
	}

	public void setSex(char sex) {
		this.sex = sex;
	}

	public void showMyself() {
		System.out.println("name=" + name + ",age=" + age + ",sex=" + sex);
	}

}

class Student extends Person {
	public Student() {
	}
		
	public Student(String name, int age, char sex) {
		super(name, age, sex);
	}

	public void showMyself() {
		System.out.println("Student:name=" + name + ",age=" + age + ",sex=" + sex);
	}
}

class Teacher extends Person {
	public Teacher() {

	}
	
	public Teacher(String name, int age, char sex) {
		super(name, age, sex);
		// TODO Auto-generated constructor stub
	}

	public void showMyself() {
		System.out.println("Teacher:name=" + name + ",age=" + age + ",sex=" + sex);
	}
}
```

### 1016==类成员变量及其应用==

```java
import java.util.Scanner;

public class Main {
	public static void main(String args[]) {
		Scanner cin = new Scanner(System.in);
		String name = cin.next();
		int age = cin.nextInt();
		Person p1 = new Person(name, age);
		name = cin.next();
		age = cin.nextInt();
		p1.print();
		Person p2 = new Person(name, age);
		p2.print();
		p2.finalize(p1);
		p2.print();
	}
}

class Person {
	String name;
	int age;
	static int count = 0;

	public Person() {

	}

	public Person(String name, int age) {
		this.name = name;
		this.age = age;
		Person.count++;
	}

	public void print() {
		howMany();
		System.out.println(toString());

	}

	public static void howMany() {
		System.out.println("Person.count=" + Person.count);
	}

	@Override
	public String toString() {
		return this.name + "," + this.age;
	}
	public void finalize(Person person) {
		count-=1;
		System.out.println("Release("+person.name+","+person.age+")");
	}

}
```

### 1017==抽象类的应用==

```java
import java.util.Scanner;

public class Main{

public static void main(String args[])throws Exception{

     Scanner cin=new Scanner(System.in);

     double radius_a=cin.nextDouble();

     double radius_b=cin.nextDouble();

     Shape g=new Ellipse(radius_a,radius_b);

     g.print();

     double height=cin.nextDouble();

     double width=cin.nextDouble();

     g=new Rectangle(height,width);

     g.print();
	}

}
abstract class Shape{
	double shape;
	abstract double area();
	abstract double perimeter();
	abstract void print();
}
class Ellipse extends Shape{
	double radius_a;
	double radius_b;
	
	public Ellipse(double radius_a, double radius_b) {
		super();
		this.radius_a = radius_a;
		this.radius_b = radius_b;
	}
	
	public double getRadius_a() {
		return radius_a;
	}
	public void setRadius_a(double radius_a) {
		this.radius_a = radius_a;
	}
	public double getRadius_b() {
		return radius_b;
	}
	public void setRadius_b(double radius_b) {
		this.radius_b = radius_b;
	}
	@Override
	public double area() {
		return 3.14*radius_a*radius_b;
		
	}
	@Override
	public double perimeter() {
		return 3.14*(radius_b+radius_a);
	}
	@Override
	public void print() {
		System.out.println("Ellipse:area="+area()+",perimeter="+perimeter());
	
	}	
}
class Rectangle extends Shape{
	double height;
	double width;
	
	
	public Rectangle(double height, double width) {
		super();
		this.height = height;
		this.width = width;
	}
	
	
	public double getHeight() {
		return height;
	}


	public void setHeight(double height) {
		this.height = height;
	}


	public double getWidth() {
		return width;
	}


	public void setWidth(double width) {
		this.width = width;
	}


	@Override
	public double area() {
		return this.width*this.height;
		
	}
	@Override
	public double perimeter() {
		return (this.width+this.height)*2;
		
	}
	@Override
	public void print() {
		System.out.println("Rectangle:area="+area()+",perimeter="+perimeter());
	
	}
	
}
```

### 1018==圆面积和球的体积==

```java
import java.util.Scanner;

public class Main {
	public static void main(String args[]) {
		Scanner cin=new Scanner(System.in); 
		double r=cin.nextDouble();
		double s,v;
		double p=3.14;
		s=r*r*p;
		v=4.00/3.00*p*r*r*r;
		System.out.println("area="+s);
		System.out.println("volume="+v);
	}
}
```

### 1019==输出其平方根==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		double x, root,r;
		Scanner cin = new Scanner(System.in);
		x=cin.nextDouble();
		r=Math.sqrt(x);
		root=r*1.0;
		System.out.println("The square root of " + x + " is " + root);
	}
}
```

### 1020==华氏温度和摄氏温度的转化==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		 double x,root; 
		 Scanner cin=new Scanner(System.in); 
		 double f,c; 
		 f=cin.nextDouble();
		 c=(f-32)/1.8;
		 System.out.println("The temprature is "+c); 
	}
}
```

### 1021==大写小写字母输出==

```java
import java.util.Scanner;

/*自己原来做的方法
public class Main {
	public static void main(String[] args) {
		char ch; 
		Scanner cin=new Scanner(System.in);
		String c=cin.next(); 
		ch=c.charAt(0);
		ch+=32;
		System.out.println(ch);  
	}
}
*/

//与题目符合的做法
public class Main {
	public static void main(String[] args) throws Exception {
		char ch;
		ch = (char) System.in.read();
		ch += 32;
		System.out.println(ch);
	}
}
```

### 1022==计算存款利息==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int money,year; 
		double interest,rate; 
		Scanner sc=new Scanner(System.in); 
		money=sc.nextInt();
		year=sc.nextInt();
		rate=sc.nextDouble();		
		interest=money*Math.pow(1+rate,year)-money;
		System.out.println("interest="+(int)(interest*100+0.5)/100.0); 
	}
}
```

### 1023==计算一个3位数的各位数字==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int num = sc.nextInt();
		int h=num/100;
		int t=num%100/10;
		int o=num%100%10;
		System.out.println("hundred="+h+",ten="+t+",one="+o); 
	}
}
```

### 1024==显示两级成绩==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) throws Exception {
		int ri, repeat;
		int mark;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (ri = 1; ri <= repeat; ri++) {
			mark = in.nextInt();
			if (mark < 60) {
				System.out.println("F");
			} else {
				System.out.println("P");
			}
		}
	}
}
```

### 1025==求三角形的面积和周长==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args){
		int ri,repeat; 
		float a,b,c,area,primeter,s; 
		Scanner in=new Scanner(System.in); 
		repeat=in.nextInt(); 
		for(ri=1;ri<=repeat;ri++){ 
		a=in.nextFloat(); 
		b=in.nextFloat(); 
		c=in.nextFloat();
		primeter=a+b+c;
		s=(a+b+c)/2; 
		area=(float)Math.sqrt(s*(s-a)*(s-b)*(s-c));
		if (a+b>c && a+c>b && b+c>a) {
			System.out.println("area="+(int)(area*100+0.5)/100.+";perimeter="+(int)(primeter*100+0.5)/100.);
		}else {
			System.out.println("These sides do not correspond to a valid triangle!");
		}
		
	}
	}
}

```

### 1026==计算个人所得税==

```java
import java.text.DecimalFormat;
import java.util.Scanner;

public class Main {
	public static void main(String[] args){
		int ri,repeat; 
		float rate,salary,tax; 
		Scanner in=new Scanner(System.in); 
		repeat=in.nextInt(); 
		rate=0;
		for(ri=1;ri<=repeat;ri++){ 
		salary=in.nextFloat(); 
		if (salary<=850) {
			rate=0;
		} else if(850<salary && salary<=1350){
			rate=0.05f;
		}else if (1350<salary && salary<=2850) {
			rate=0.1f;
		}else if (2850<salary && salary<=5850) {
			rate=0.15f;
		}else if (5850<salary) {
			rate=0.2f;
		}
		tax=rate*(salary-850); 
		System.out.println("tax="+(int)(tax*100+0.5)/100.0); 
		}
	}
}

```

### 1027==显示水果的价格==

```java
import java.text.DecimalFormat;
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int ri, repeat;
		int choice;
		float price=0;
		String a = null;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (ri = 1; ri <= repeat; ri++) {
			choice = in.nextInt();
			switch (choice) {
			case 1:
				a="[1]apples";
				price=3.0f;
				break;
			case 2:
				a="[2]pears";
				price=2.5f;
				break;
			case 3:
				a="[3]oranges";
				price=4.1f;
				break;
			case 4:
				a="[4]grapes";
				price=10.2f;
				break;
			default:
				break;
			}
			System.out.println(a + ",price=" + price);
		}
	}
}

```

### 1028==五级记分制成绩对应的百分制区间==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat;
		char ch;
		String result;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		result=null;
		for (int ri = 1; ri <= repeat; ri++) {
			ch=(in.next()).charAt(0);
			switch (ch) {
			case 'A':
				result="90-100";
				break;
			case 'B':
				result="80-89";
				break;
			case 'C':
				result="70-79";
				break;
			case 'D':
				result="60-69";
				break;
			case 'E':
				result="0-59";
				break;
				
			default:
				result="Invalid input";
				break;
			}
			System.out.println(result);
		}
	}
}

```

### 1029==求n的阶乘n!==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat;
		double s;
		int n=0;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			s=1;
			n=in.nextInt();
			for (int i = 1; i <= n; i++) {
				s=i*s;
			}
			System.out.println(s*1.0);
		}
		
	}
}
```

### 1030==求数列的奇数和==<span style="color:red;">★★</span>

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int ri, repeat;
		int x, sum;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (ri = 1; ri <= repeat; ri++) {
			sum = 0;
			while (true) {
				x = in.nextInt();
				if (x <= 0)
					break;
				if (x % 2 == 0)
					continue;
				else
					sum = sum + x;
			}
			System.out.println(sum);
		}

	}
}

```

### 1031==求整数的位数以及各位数之和==<span style="color:red;">★★</span>

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat,n,num,sum;
		int i;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			n=Math.abs(in.nextInt());
			num=1;
			sum=0;
			i=10;
			while(true){
				if (n<10) {
					sum=n;
					num=1;
					break;
				}
				if (n/i==0) 
					break;					
				else if ((n/i)<10)
					sum+=n/i;
				sum+=((n%i)/(i/10));
				num+=1;
				i=i*10;
			}			
			System.out.println("number="+num+",sum="+sum);
		}
	}
}

```

### 1032==求a+aa+aaa+aaaa+......a==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat,n,sum,a,j;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			a=Math.abs(in.nextInt());
			n=Math.abs(in.nextInt());
			int []nums=new int[n];
			nums[0]=a;
			j=10;sum=0;
			for (int i = 0; i < nums.length-1; i++) {
				nums[i+1]=nums[i]+a*j;
				j=j*10;
			}		
			for (int i = 0; i < nums.length; i++) {
				sum+=nums[i];
				if (i==0) {
					System.out.print(nums[i]);
				}else if (i==nums.length-1) {
					System.out.print("+"+nums[i]+"="+sum);
				}else {
					System.out.print("+"+nums[i]);
				}				
			}
		}
	}
}

```

### 1033==判断素数==

```java
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		int repeat,n;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			n=in.nextInt();
			System.out.println(prime(n));
		}
	}

	public static String prime(int n) {
		boolean istrue=true;
		if (n<2) {
			return "No";
		}
		for (int i = 2; i * i <= n; i++) {
			if (n % i == 0) {
				istrue=false;
				return "No";		
			}
		}
		if (istrue) {
			return "Yes";
		}
		return null;		
	}
}

```

### 1034==输出Fibonacci序列==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat,m,n,f,i,ri;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (i = 1; i <= repeat; i++) {
			n=in.nextInt();
			m=in.nextInt();
			f=1;
			ri=1;
			while(f<=m) {
				if (f>=n)
					System.out.print(f+" ");
				f=fib(ri);
				ri++;
			}
			System.out.println();
		}
	}

	public static int fib(int n) {
		int f1=1,f2=1,f3=0;
		if (n<2) {
			return 1;
		}
		for(int i=3;i <=n;i++) {
			f3=f2+f1;
			f1=f2;
			f2=f3;			
		}
		return f3;		
	}
	
}
/*import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			String sumString="";
			int n=in.nextInt();
			int m=in.nextInt();
			for (int i = 1; i <50-1; i++) {				
				if (Integer.parseInt(fib(i))>=n&&Integer.parseInt(fib(i))<=m) {
					sumString+=(" "+fib(i));
					continue;
				}
			}
			System.out.println(sumString.substring(1));
		}
	}

	private static String fib(int n) {
		int []nums=new int[50];
		nums[0]=1;
		nums[1]=1;
		int i = 2;
		while (i < nums.length) {
			nums[i]= nums[i-1]+nums[i-2];
				i++;
		}
		
		return nums[n-1]+"";		
	}
	
}*/
```

### 1035==求完数==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat,n,m;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			String str="";
			m=in.nextInt();
			n=in.nextInt();
			for (int i = m; i <=n; i++) {
				if (i==factorsum(i)) {
					System.out.print(i+" ");
				}
			}
			System.out.println();
		}in.close();
		
	}

	private static int factorsum(int n) {
		int sum=1;
		for (int i = 2; i< n; i++) {
			if (n%i==0) {
				sum+=i;
			}
		}
		return sum;
	}	
}
```

### 1036==十进制转二进制==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int repeat,n;
		Scanner in = new Scanner(System.in);
		repeat = in.nextInt();
		for (int ri = 1; ri <= repeat; ri++) {
			n=in.nextInt();
			System.out.println(dectobin(n));
		}
	}

	private static String dectobin(int n) {
		String str="";
		do {
			str=n%2+str;
			n=n/2;
		} while (n!=0);
		return str;
	}
	
}
```

### 1037==类与对象==

```java
import java.util.Scanner;

public class Main{

public static void main(String args[]) {
	Scanner sc=new Scanner(System.in);
	int year1=sc.nextInt();
	int month1=sc.nextInt();
	int day1=sc.nextInt();
	Date date1=new Date();
	date1.setDate(year1, month1, day1);
	int year2=sc.nextInt();
	int month2=sc.nextInt();
	int day2=sc.nextInt();
	Date date2=new Date();
	date2.setDate(year2, month2, day2);
	date1.Print();
	date2.Print();
	if (date1.equals(date2)) {
		System.out.println("Two date is equals:true");
	}else {
		System.out.println("Two date is equals:false");
	}

}
}
class Date{
	int year;
	int month;
	int day;
	void setDate(int year,int month,int day){
		this.year=year;
		this.month=month;
		this.day=day;
	}
	void Print(){
		System.out.println("Date:"+year+"-"+month+"-"+day);
	}
	boolean equals(Date d2) {
		if (d2.year==this.year&&d2.month==this.month&&d2.day==this.day) {
			return true;
		}else {
			return false;
		}
	}
}
```

### 1038==类变量的使用方法==

```java
import java.util.Scanner;

public class Main{

public static void main(String args[]) {
	Scanner sc=new Scanner(System.in);
	String name=sc.next();
	int age=sc.nextInt();
	String name2=sc.next();
	int age2=sc.nextInt();
	Person person1=new Person(name, age);
	person1.howMany();
	System.out.println(person1.toString());
	Person person2=new Person(name2, age2);
	person2.howMany();
	System.out.println(person2.toString());
	person1.finalize(person1);
	person2.howMany();
}
}
class Person{
	String name;
	int age;
	static int count;
	public Person(String name, int age) {
		this.name = name;
		this.age = age;
		count+=1;
	}
	public String toString() {
		return this.name+","+this.age+"years";
	}
	public void howMany() {
		System.out.print("Person.count="+count+",");
	}
	public void finalize(Person person) {
		count-=1;
		System.out.println("release object("+person.name+","+person.age+"years)");
	}
	public void print() {
		howMany();
		toString();
	}
}
```

### 1039==类的继承==

```java
import java.util.Scanner;

public class Main{

public static void main(String args[]) {
	Scanner sc=new Scanner(System.in);
	String name=sc.next();
	int age=sc.nextInt();
	boolean sex=sc.nextBoolean();
	int num=sc.nextInt();
	String major=sc.next();
	Student sd1=new Student(name, age, sex, num, major);
	System.out.println("Name:"+sd1.getName()+",Age:"+sd1.getAge()+",Sex:"+sd1.isSex()+",StuNumber:"+sd1.getNum()+",Major:"+sd1.getMajor());
}
}
class Person{
	private String name;
	private int age;
	private boolean sex;
	public Person(String name, int age, boolean sex) {
		super();
		this.name = name;
		this.age = age;
		this.sex = sex;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	public boolean isSex() {
		return sex;
	}
	public void setSex(boolean sex) {
		this.sex = sex;
	}
}
class Student extends Person{
	private int num;
	private String major;
	public Student(String name, int age, boolean sex, int num, String major) {
		super(name, age, sex);
		this.num = num;
		this.major = major;
	}
	public int getNum() {
		return num;
	}
	public void setNum(int num) {
		this.num = num;
	}
	public String getMajor() {
		return major;
	}
	public void setMajor(String major) {
		this.major = major;
	}
}
```

### 1040==方法重载==

```java
import java.util.Scanner;

public class Main{

public static void main(String args[]) {
	Scanner sc=new Scanner(System.in);
	String name=sc.next();
	int age=sc.nextInt();
	String name2=sc.next();
	int age2=sc.nextInt();
	int num=sc.nextInt();
	String major=sc.next();
	
	Person person=new Person();
	Student sd1=new Student();
	person.setInfo(name);
	person.setInfo(name, age);
	person.showMyself();
	sd1.setInfo(name2);
	sd1.setInfo(name2, age2);
	sd1.setInfo(name2, age2, num, major);
	sd1.showMyself();
	
}
}
class Person{
	String name;
	int age;
	public void setInfo(String n) {
		this.name=n;
	}
	
	public void setInfo(String n, int a) {
		// TODO Auto-generated method stub
		this.name=n;
		this.age=a;
	}
	
	public void showMyself() {
		System.out.println("name="+this.name+",age="+this.age);
	}
}
class Student extends Person{
	int num;
	String major;
	
	public void setInfo(String n,int a,int k,String m) {
		this.name=n;
		this.age=a;
		this.num=k;
		this.major=m;
		
	}
	@Override
	public void showMyself() {
		System.out.println("name="+this.name+",age="+this.age+",num="+this.num+",major="+this.major);
	}
	
	
}
```

### 1041==static静态变量及方法的应用==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		String p1=in.next();
		String p2=in.next();
		Person person1=new Person(p1);
		person1.dispInfo();
		Person person2=new Person(p2);
		person2.dispInfo();
		person1.currentCount();
	}	
}
class Person{
	private static int count=100;
	private final static String country; 
	private int id;private String name;
	static{country="CHINA";}
	public Person(String name) {
		this.name=name;
		this.id=count;
		count+=1;
	}
	public static void currentCount() {
		System.out.println("The current count:"+count);
	}
	public void dispInfo() {
		System.out.println("ID:"+this.id+",COUNTRY:"+this.country+",NAME:"+this.name);
	}
	
}
```

### 1042==对象多态和多态方法的应用==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		String cat1=in.next();
		String cat2=in.next();
		String dog1=in.next();
		String dog2=in.next();
		String lady1=in.next();
		String lady2=in.next();
		Cat cat=new Cat(cat1, cat2);
		Dog dog=new Dog(dog1, dog2);
		Lady lady=new Lady(lady1, cat);
		Lady lady3=new Lady(lady2, dog);
		lady.myPetShow();
		lady3.myPetShow();
	}	
}

class Animal{
	private String name;
	public Animal(String name) {
		this.name=name;
	};
	public String getName() {
		return this.name;
	}
	public String disp() {
		return toString();
	}
}
class Cat extends Animal{
	String eyeColor;
	static String cry="MiaoWu!";

	public Cat(String name, String eyeColor) {
		super(name);
		this.eyeColor = eyeColor;
	}	
	public String getEyeColor() {
		return this.eyeColor;
	}
	public String disp() {
		return "pet:Cat:"+this.getName()+",eyeColor:"+this.getEyeColor()+",Cry:"+this.cry;
	}
}
class Dog extends Animal{
	String furColor;
	static String cry="WangWang!";
	
	public Dog(String name, String furColor) {
		super(name);
		this.furColor = furColor;
	}
	public String getFurColor() {
		return this.furColor;
	}
	public String disp() {
		return "pet:Dog:"+this.getName()+",furColor:"+this.getFurColor()+",Cry:"+this.cry;
	}
}
class Lady{
	private String name;
	private Animal pet;
	public Lady(String name, Animal pet) {
		this.name = name;
		this.pet = pet;
	}
	public void myPetShow() {
		System.out.println(this.name+pet.disp());
	}
	
}
```

### 1043==接口及其实现==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		String na1 = in.next();
		String na2 = in.next();
		CameraPhone nokiaPhone = new NokiaPhone();
		CameraPhone motoPhone = new MotoPhone();
		Student st1 = new Student(na1, nokiaPhone);
		Student st2 = new Student(na2, motoPhone);
		System.out.println(st1.myCall());
		System.out.println(st2.myCall());
		System.out.println(st1.myTakePhoto());
		System.out.println(st2.myTakePhoto());
		System.out.println(st1.myReceive());
		System.out.println(st2.myReceive());
	}
}

interface MobilePhone {
	String call();

	String receive();

	String sendMessage();

	String receiveMsg();
}

interface Camera {
	String takePhoto();
}

interface CameraPhone extends MobilePhone, Camera {

}

class NokiaPhone implements CameraPhone {

	public String call() {
		// TODO Auto-generated method stub
		return "Nokia call";
	}

	public String receive() {
		// TODO Auto-generated method stub
		return "Nokia receive";
	}

	public String sendMessage() {
		// TODO Auto-generated method stub
		return "Nokia sendMessage";
	}

	public String receiveMsg() {
		// TODO Auto-generated method stub
		return "Nokia receiveMsg";
	}

	public String takePhoto() {
		// TODO Auto-generated method stub
		return "Nokia takePhoto";
	}
}

class MotoPhone implements CameraPhone {

	public String call() {
		// TODO Auto-generated method stub
		return "Moto call";
	}

	public String receive() {
		// TODO Auto-generated method stub
		return "Moto receive";
	}

	public String sendMessage() {
		// TODO Auto-generated method stub
		return "Moto sendMessage";
	}

	public String receiveMsg() {
		// TODO Auto-generated method stub
		return "Moto receiveMsg";
	}

	public String takePhoto() {
		// TODO Auto-generated method stub
		return "Moto takephone";
	}
}

class Student {
	String Name;
	CameraPhone myPhone;

	public Student(String name, CameraPhone myPhone) {
		super();
		Name = name;
		this.myPhone = myPhone;
	}

	public String myCall() {
		return this.Name + " use " + myPhone.call();
	}

	public String myReceive() {
		return this.Name + " use " + myPhone.receive();
	}

	public String mySendMessage() {
		return this.Name + " use " + myPhone.sendMessage();
	}

	public String myReceiveMsg() {
		return this.Name + " use " + myPhone.receiveMsg();
	}

	public String myTakePhoto() {
		return this.Name + " use " + myPhone.takePhoto();
	}

}
```

### 1044==try...catch...finally捕获异常==

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {		
		Scanner in=new Scanner(System.in);		
		try {
			int a=in.nextInt();
			int b=in.nextInt();
			int sum=a/b;
			System.out.println(a+"/"+b+"="+sum);
		}catch(InputMismatchException err2) {			
			System.out.println("Error,please input integer!");	
		}catch(ArithmeticException err1) {
			System.out.println("The vivisor can not be 0.");		
		}
		finally {
			System.out.println("No matter whether there is an exception or not,the program is executed.");
		}
	}	
}
	

```

### 1045==主动抛出一个数据溢出异常==

```java

public class Main {
	public static void main(String[] args) {
		for (byte i = 1; i < 10; i++) {
			calc(i);
		}
	}

	static byte factorial(byte k){
		byte sum = 1;
		for (byte j = 1; j <= k; j++) {
			sum *= j;
		}
		return sum;
	}

	static void calc(byte k) {
		try {
			if (factorial(k)<0) {
				throw new ValueException("exception:overflow");
				
			}else {
				System.out.println(k + "!=" + factorial(k));
			}			
		} catch (ValueException e) {
			System.out.println(e.getMessage());
		}
	}
	
}
class ValueException extends Exception{
	public ValueException() {
	}
	public ValueException(String message) {
		super(message);

	}

	
}
	

```

### 1046==泛型的应用==对于泛型理解还不够

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		int b1=in.nextInt();
		String b2=in.next();
		double b3=in.nextDouble();
		String b4name=in.next();
		int b4age=in.nextInt();
		Student student=new Student(b4name,b4age);
		Box box1=new Box(b1);
		Box box2=new Box(b2);
		Box box3=new Box(b3);
		Box box4=new Box(student);
		box1.print();
		box2.print();
		box3.print();
		box4.print();
}
}
class Box<T>{
	T t;
	
	public Box(T t) {
		super();
		this.t = t;
	}
	void setT(T t){
		this.t=t;
	}
	T getT(){
		return this.t;
	}
	void print(){
		System.out.println(this.t);
	}
}	
class Student{
	String name;
	int age;
	public Student(String name, int age) {
		super();
		this.name = name;
		this.age = age;
	}
	@Override
	public String toString() {
		return "Name:" + name + ",Age:" + age;
	}
	
}

```

### 1047==集合List之ArrayList==

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		String id=in.next();
		String name=in.next();
		double salary=in.nextDouble();
		String id2=in.next();
		String name2=in.next();
		double salary2=in.nextDouble();
		String id3=in.next();
		String name3=in.next();
		double salary3=in.nextDouble();
		Staff staff=new Staff(id,name,salary);	
		Staff staff2=new Staff(id2,name2,salary2);	
		Staff staff3=new Staff(id3,name3,salary3);
		List<Staff>staffs=new ArrayList<Staff>();
		staffs.add(staff);
		staffs.add(staff2);
		staffs.add(staff3);
		for (Staff s:staffs) {
			System.out.println(s.toString());
		}
	}
}

class Staff {
	String sid;
	String name;
	double salary;
		
	public Staff(String sid, String name, double salary) {
		super();
		this.sid = sid;
		this.name = name;
		this.salary = salary;
	}

	@Override
	public String toString() {
		return "ID:" + sid + ",Name:" + name + ",Salary:" + salary;
	}
}
```

### 1048==集合List之LinkedList==

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;
import java.util.ListIterator;
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		String b1ISBN=in.next();
		String b1Title=in.next();
		String b1Author=in.next();
		double b1Price=in.nextDouble();
		String b2ISBN=in.next();
		String b2Title=in.next();
		String b2Author=in.next();
		double b2Price=in.nextDouble();
		String b3ISBN=in.next();
		String b3Title=in.next();
		String b3Author=in.next();
		double b3Price=in.nextDouble();
		Book book1=new Book(b1ISBN, b1Title, b1Author, b1Price);
		Book book2=new Book(b2ISBN, b2Title, b2Author, b2Price);
		Book book3=new Book(b3ISBN, b3Title, b3Author, b3Price);
		List<Book>books=new LinkedList<Book>();
		books.add(book1);
		books.add(book2);
		books.add(book3);
		String finder=in.next();
		
		Iterator<Book> iterator=books.iterator();
		ListIterator<Book> iterator2=books.listIterator();
		System.out.println("----LinkedList----");
		while (iterator.hasNext()) {
			System.out.println(iterator.next().toString());
		}
		System.out.println("---find---");
		while (iterator2.hasNext()) {
			if (iterator2.next().toString().indexOf(finder)!=-1) {
				System.out.println("find:"+iterator2.previous());
				break;
			}
		}
		
		
	}
}
class Book{
	String ISBN;
	String title;
	String author;
	double price;
	public Book(String iSBN, String title, String author, double price) {
		super();
		ISBN = iSBN;
		this.title = title;
		this.author = author;
		this.price = price;
	}
	
	public String getISBN() {
		return ISBN;
	}

	public void setISBN(String iSBN) {
		ISBN = iSBN;
	}

	public String getTitle() {
		return title;
	}

	public void setTitle(String title) {
		this.title = title;
	}

	public String getAuthor() {
		return author;
	}

	public void setAuthor(String author) {
		this.author = author;
	}

	public double getPrice() {
		return price;
	}

	public void setPrice(double price) {
		this.price = price;
	}

	@Override
	public String toString() {
		return "ISBN:" + ISBN + ",Title:" + title + ",Author:" + author + ",Price:" + price;
	}
	
	
}

```

### 1049==集合Set之TreeSet==

```java
import java.util.Comparator;
import java.util.Scanner;
import java.util.Set;
import java.util.TreeSet;


public class Main {
	public static void main(String[] args) {
			Scanner sc=new Scanner(System.in);
			String no=sc.next();
			String name=sc.next();
			double score=sc.nextDouble();
			String no1=sc.next();
			String name1=sc.next();
			double score1=sc.nextDouble();
			String no2=sc.next();
			String name2=sc.next();
			double score2=sc.nextDouble();
			Student student1=new Student(no,name,score);
			Student student2=new Student(no1,name1,score1);
			Student student3=new Student(no2,name2,score2);
			Student[] students={student1,student2,student3};
			Set<Student>st=new TreeSet<Student>(new StuCompareScore());
			for (int i = 0; i < students.length; i++) {
				st.add(students[i]);				
			}
			System.out.println("--TreeSet--");
			for (Student s:st) {
				System.out.println(s.toString());
			}
			st=new TreeSet<Student>(new stuCompareNo());
			for (int i = 0; i < students.length; i++) {
				st.add(students[i]);				
			}
			System.out.println("--TreeSet--");
			for (Student s:st) {
				System.out.println(s.toString());
			}
			
	}
}
class Student{
	String no;
	String name;
	double score;
	public Student(String no, String name, double score) {
		this.no = no;
		this.name = name;
		this.score = score;
	}
	
	public String toString() {
		return "No:" + no + ",Name:" + name + ",Score:" + score;
	}	
	
}
class StuCompareScore implements Comparator<Student>{
    
	
	public int compare(Student o1, Student o2) {
		return (int) (o2.score-o1.score);
	}
}
class stuCompareNo implements Comparator<Student>{

	
	public int compare(Student o1, Student o2) {
		return o1.no.compareTo(o2.no);
	}
	
}
```

### 1050==集合Set之HashSet==

```java
import java.util.Comparator;
import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;



public class Main {
	public static void main(String[] args) {
			Scanner sc=new Scanner(System.in);
			String no=sc.next();
			String name=sc.next();
			int age=sc.nextInt();
			String no1=sc.next();
			String name1=sc.next();
			int age1=sc.nextInt();
			
			Student student1=new Student(no,name,age);
			Student student2=new Student(no1,name1,age1);
			Student[] students={student1,student2};
			Set<Student>st=new HashSet<Student>();
			for (int i = 0; i < students.length; i++) {
				st.add(students[i]);
			}
			System.out.println("--HashSet--");
			for (Student s:st) {
				System.out.println(s);
			}
			
	}
}
class Student{
	String no;
	String name;
	int age;
	
	public Student() {
		
	}
	public Student(String no, String name, int age) {
		super();
		this.no = no;
		this.name = name;
		this.age = age;
	}
	
	public String getNo() {
		return no;
	}

	public void setNo(String no) {
		this.no = no;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}

	
	public String toString() {
		return "Student:no=" + no + ",name=" + name + ",age=" + age;
	}
	
	public int hashCode() {
		final int prime = 31;
		int result = 1;
		result = prime * result + ((no == null) ? 0 : no.hashCode());
		return result;
	}
	
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Student other = (Student) obj;
		if (no == null) {
			if (other.no != null)
				return false;
		} else if (!no.equals(other.no))
			return false;
		return true;
	}
	
	
}
```

### 1051==集合Map之HashMap==

```java
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Scanner;
import java.util.Set;


public class Main {
	public static void main(String[] args) {
		Scanner sin=new Scanner(System.in);
		String []countries= {new String("Japan"),new String("Germany"),new String("China")};
		String []capitals= {new String("Yokyo"),new String("Berlin"),new String("BeiJing")};
		Map<String,String>m=new HashMap<String,String>();
		m.put(countries[0],capitals[0]);
		m.put(countries[1],capitals[1]);
		m.put(countries[2],capitals[2]);
		String n=sin.next();
		findCity(m,n);
		
		
	}

	private static  void findCity(Map<String,String> m,String n) {
		Set<String> setCitys=m.keySet();
		Iterator<String> it=setCitys.iterator();
		boolean flag=false;
		while (it.hasNext()) {
			
			String country=it.next().toString();
			if (country.equals(n)) {
				System.out.println(m.get(n));
				flag=true;
				break;
			}			
		}
		if (flag==false) {
			System.out.println("Not find!");
		}

		
	}
}
```

### 1052==集合Map之TreeMap==

```java

import java.util.Iterator;
import java.util.Map;
import java.util.Scanner;
import java.util.Set;
import java.util.TreeMap;

public class Main {
	public static void main(String[] args) {
		Scanner sin = new Scanner(System.in);
		int[] nums = { 5, 1, 6, 2, 7, 3, 8, 4, 9, 10 };
		String[] numStrings = { "five", "one", "six", "two", "seven", "three", "eight", "four", "nine", "ten" };
		Map<Integer, String> m = new TreeMap<Integer, String>();
		m.put(nums[0], numStrings[0]);
		m.put(nums[1], numStrings[1]);
		m.put(nums[2], numStrings[2]);
		m.put(nums[3], numStrings[3]);
		m.put(nums[4], numStrings[4]);
		m.put(nums[5], numStrings[5]);
		m.put(nums[6], numStrings[6]);
		m.put(nums[7], numStrings[7]);
		m.put(nums[8], numStrings[8]);
		m.put(nums[9], numStrings[9]);

		int n = sin.nextInt();
		printnum(m);
		findnum(m, n);

	}

	private static void printnum(Map<Integer, String> m) {
		System.out.println("--TreeMap--");
		Set<Integer> setNums = m.keySet();
		Iterator<Integer> it = setNums.iterator();
		while (it.hasNext()) {

			int num = it.next();
			String numString = m.get(num);
			System.out.println(num+"->"+numString);
		}
	}

	private static void findnum(Map<Integer, String> m, int n) {
		System.out.println("--SearchTreeMap--");
		Set<Integer> setNums = m.keySet();
		Iterator<Integer> it = setNums.iterator();
		boolean flag = false;
		while (it.hasNext()) {

			int num = it.next();
			if (num == n) {
				System.out.println(m.get(n));
				flag = true;
				break;
			}
		}
		if (flag == false) {
			System.out.println("Not find!");
		}

	}
}
```

### 1053==类与对象-银行帐户==

```java
import java.util.Scanner;


public class Main {
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);
		Account account=new Account();
		account.setId(101);
		double money=in.nextDouble();
		double nums1=in.nextDouble();
		double nums2=in.nextDouble();
		account.setBalance(money);
		account.inPut(nums1);
		account.outPut(nums2);
		
	}
}
class Account{
	private int id;
	private double balance;
	private double annulRate;
	
	public Account() {
		
	}
	public Account(int id,double balance) {
		super();
		this.id=id;
		this.balance = balance;	 
	}
	
	public int getId() {
		return id;
	}
	public void setId(int id) {
		this.id = id;
	}
	public double getBalance() {
		return balance;
	}
	public void setBalance(double balance) {
		this.balance = balance;
	}
	public double getAnnulRate() {
		return annulRate;
	}
	public void setAnnulRate(double annulRate) {
		this.annulRate = annulRate;
	}
	public void inPut(double nums){
		this.balance+=nums;
		System.out.println("Desposit money:"+nums+",the balance is:"+this.balance);
	}
	public void outPut(double nums) {
		if (this.balance<nums) {
			System.out.println("The Balance is not enough!");
		}else {
			this.balance-=nums;
			System.out.println("Withdraw money:"+nums+",the balance is:"+this.balance);
		}
	}
	
}

```
### 1054==类与对象(Circle)==

```java
import java.util.Scanner;

public class Main{

public static void main(String args[])throws Exception{
	 Circle circle=new Circle();
     System.out.println(circle.getRadius());
     Scanner cin=new Scanner(System.in);
     double r=cin.nextDouble();
     circle.setRadius(r);
     System.out.printf("%.2f\n",circle.getArea());
     System.out.printf("%.2f\n",circle.getPerimeter());

	}

}
class Circle{
	double centerX;
	double centerY;
	double radius;
	public Circle(){
		this(1.00);
	}
	public Circle(double radius) {
		this.radius = radius;
	}
	
	public double getRadius() {
		return this.radius;
	}
	public void setRadius(double radius) {
		this.radius = radius;
	}
	public double getArea() {
		return this.radius*this.radius*Math.PI;
	}
	
	public double getPerimeter() {
		return 2*this.radius*Math.PI;
	}
}

```

### 1055==类的继承-动物==

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sin=new Scanner(System.in);
		int birdSwing=sin.nextInt();
		int fishFins=sin.nextInt();
		int dogLegs=sin.nextInt();
		Bird bird=new Bird(birdSwing);
		Fish fish=new Fish(fishFins);
		Dog dog=new Dog(dogLegs);
		bird.fly();
		fish.swim();
		dog.walk();
		
	}
}

class Animal {
	String name;

	public void eat() {
		System.out.println("I can eat anything.");
	}
}

class Bird extends Animal {
	int numberOfWings;
	
	public Bird(int numberOfWings) {
		super.name=name;
		this.numberOfWings = numberOfWings;
	}
	public void fly() {
		System.out.println("The bird has "+this.numberOfWings+" wings,can fly;");

	}
}
class Fish extends Animal {
	int numberOfFins;
	
	public Fish(int numberOfFins) {
		super.name=name;
		this.numberOfFins = numberOfFins;
	}
	public void swim(){
		System.out.println("The fish has "+this.numberOfFins+" fins,can swim;");

	}
}
class Dog extends Animal {
	int numberOfLegs;
	public Dog(int numberOfLegs) {
		super.name=name;
		this.numberOfLegs = numberOfLegs;
	}
	public void walk() {
		System.out.println("The dog has "+this.numberOfLegs+" wings,can run.");

	}
}
```

### 1056==类的继承-圆柱==
```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		double ri=sc.nextDouble();
		double hi=sc.nextDouble();
		Circle circle=new Circle(ri);
		Cylinder cylinder=new Cylinder(ri,hi);
		System.out.printf("The Area of Cylinder:%.2f\n",cylinder.getArea());
		System.out.printf("The Volume of Cylinder:%.2f\n",cylinder.getVolime());
		sc.close();
	}
}
class Circle{
	double radius;
	
	public Circle() {
		
	}
	
	public Circle(double ri) {
		this.radius = ri;
	}

	public double getArea() {
		return radius*radius*Math.PI;
	}
}
class Cylinder extends Circle{
	double height;
	public Cylinder() {
	}
	
	public Cylinder(double radius, double height) {
		super(radius);
		this.height = height;
	}

	@Override
	public double getArea() {
		return 2*radius*height*Math.PI;
	}
	
	public double getVolime() {
		// TODO Auto-generated method stub
		return super.getArea()*height;
	}
}
```
### 1057==接口与实现--员工年龄降序==
```java
import java.util.Arrays;
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		int id,age;
		String name;
		Scanner sc = new Scanner(System.in);
		id = sc.nextInt();
		name = sc.next();
		age = sc.nextInt();
		Employee employee1=new Employee(id, name, age);
		id = sc.nextInt();
		name = sc.next();
		age = sc.nextInt();
		Employee employee2=new Employee(id, name, age);
		id = sc.nextInt();
		name = sc.next();
		age = sc.nextInt();
		Employee employee3=new Employee(id, name, age);
		Employee[] employees = new Employee[3];
		employees[0]=employee1;
		employees[1]=employee2;
		employees[2]=employee3;
		Arrays.sort(employees);
		System.out.println("Sorted by age!");
		for (Employee e:employees) {
			System.out.println(e.toString());
		}
		

	}
}

class Employee implements Comparable<Employee> {
	int id;
	String name;
	int age;

	public Employee() {
		// TODO Auto-generated constructor stub
	}

	public Employee(int id, String name, int age) {
		super();
		this.id = id;
		this.name = name;
		this.age = age;
	}

	public int getId() {
		return id;
	}

	public void setId(int id) {
		this.id = id;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}
	
	public int compareTo(Employee employee) {
		return employee.getAge()-getAge();
	}

	@Override
	public String toString() {
		return "[id=" + this.id + ", name=" + this.name + ", age=" + this.age + "]";
	}

	
	
}
```
### 1058==接口及其实现--自建比较器(Student)==
```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int id = sc.nextInt();
		String name = sc.next();
		
		int id2 = sc.nextInt();
		String name2 = sc.next();
		
		int id3 = sc.nextInt();
		String name3 = sc.next();
		
		Student[] students = new Student[] {new Student(id, name),new Student(id2, name2),new Student(id3, name3)};
		Arrays.sort(students);
		System.out.println("Sorted by id:");
		for (Student e:students) {
			System.out.println(e.toString());
		}
	
		Arrays.sort(students,new CompareName());
		System.out.println("Sorted by Name:");
		for (Student e:students) {
			System.out.println(e.toString());
		}

	}
}

class Student implements Comparable<Student>{
	int id;
	String name;

	public Student() {
		// TODO Auto-generated constructor stub
	}

	public Student(int id, String name) {
		super();
		this.id = id;
		this.name = name;
		
	}
		
	public int getId() {
		return id;
	}

	public void setId(int id) {
		this.id = id;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	
	public String toString() {
		return "Student [id=" + id + ", name=" + name + "]";
	}

	
	public int compareTo(Student student) {
		return ((this.id<student.id)?-1:(this.id==student.id?0:1));
	}
}
class CompareName implements Comparator<Student>{

	
	public int compare(Student o1, Student o2) {
		return o1.name.compareTo(o2.name);
	}
	
}
```
### 1059==内部类及匿名内部类==
```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		String s1=sc.next();
		String s2=sc.next();
		String s3=sc.next();
		String s4=sc.next();
		
		String[] ss= {s1,s2,s3,s4};
		Direction direction=new Direction(ss);
		direction.out(ss);
	}
}

class Direction{
	String[] ss;
	
	public Direction(String[] ss) {
		super();
		this.ss = ss;
	}

	class Sorter implements Comparator<String>{

		
		public int compare(String s1, String s2) {
			// TODO Auto-generated method stub
			return s1.compareTo(s2);
		}
		
	}
	
	void out(String[] ss) {
//		Direction.Sorter sorter=new Direction.Sorter();
		Arrays.sort(ss,new Comparator<String>(){

			
			public int compare(String s1, String s2) {
				return s1.compareTo(s2);
			}});
		for (String s:ss) {
			System.out.print(s+" ");
		}
//		for (String s:ss) {
//			System.out.print(s+" ");
//		}
	}
	
	
	
}

```
### 1060====
```java

```