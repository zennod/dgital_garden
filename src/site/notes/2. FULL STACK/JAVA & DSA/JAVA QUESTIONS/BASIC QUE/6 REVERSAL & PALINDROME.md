---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/basic-que/6-reversal-and-palindrome/","noteIcon":""}
---


# 1. INTEGER
```Java
public static void reverseInt(){  
Scanner sc = new Scanner(System.in);  
System.out.print("Enter an Integer Value: ");  
int num = sc.nextInt();  
int rev = 0;  
while (num != 0) {  
   rev = rev * 10 + num % 10;  
   num = num/10;  
}  
System.out.println("The reverse is : "+ rev);  
}  

public static void revIntByStrBuffer(){  

Scanner sc = new Scanner(System.in);  
System.out.print("Enter an Integer Value: ");  
int num = sc.nextInt(); 

System.out.println(new StringBuffer(String.valueOf(num)).reverse());  
}
```
***
## PALINDROME
```Java
public static void intPdrm(){  
Scanner sc = new Scanner(System.in);  
System.out.println("Enter a number");  
int num = sc.nextInt();  
int t = num;  
int rev =0;  
while (num!= 0){  
	rev = rev * 10 + num %10;  
	num = num/ 10;  
}  
if (rev == t){  
	System.out.println(" It is Palindrome Number");  
}  
else {  
	System.out.println(" it is not a Palindrome Number");  
}  
}
```
***
***
# 2. STRING
```java
public class str_rev {  
public static void main(String[] args) {  
// String is immutable  
Scanner sc = new Scanner(System.in);  
System.out.print("Enter a String: ");  
String str = sc.nextLine();  

// 1. Using for loop.  
int len = str.length();
String rev = "";  

for (int i = len-1; i>=0 ; i--) {  
	rev +=str.charAt(i);  
}  
System.out.println(rev);  



// 2. using Stringbuffer.  
StringBuffer sb = new StringBuffer(str); 
// StringBuffer mutable  
System.out.println(sb.reverse());  
}
```
***
## PALINDROME
```Java
public static void strPldr(){  
Scanner sc = new Scanner(System.in);  
System.out.print("Enter the String: ");  
String str = sc.nextLine();  

StringBuilder rev = new StringBuilder();

for (int i = (str.length())-1; i >=0 ; i--) {  
	rev.apoend(str.charAt(i));  
}  

if(str.contentEquals(rev)) {  
	System.out.println(str + " is Palindrome");  
}  
else {  
	System.out.println(str +" is not Palindrome");  
}  
}
```
