---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/2-arrays/java-array/","noteIcon":""}
---

- It is Simply a collection of the same data types.
- The Base Value is **`0`**
- The *Difference* between *2 indexes* is called as **OFFSET**
- Arrays are **MUTABLE** *(un-changeable)* because *MEMORY IS ALLOCATED DYNAMICALLY*
```Java 
int[] arr = {38,84,85,94494,68}
```
***
***
# INPUT
## 1. Integer
```java
// General
datatype[] var_name = new datatype[arr_value];
-------------------------------------------------------------------
Scanner sc = new Scanner(System.in);
// To enter how many elements you want
System.out.println("Enter how many element do you want");
int arr_range = sc.nextInt();

// Entering the elements
System.out.println("Enter the elements");
int [] arr = new int[arr_range]
for(int i= 0 ; i<arr_range; i++){
	a[i] = sc.nextInt();
}
```
***
## 2. String 
```java
Scanner sc = new Scanner(System.in);
System.out.println("Enter The Array range: ");
int arr_range= sc.nextInt();

System.out.println("Enter the Elements: ");
String[] arr = new String[arr_range];
for (i=0; i<arr_range, i++){
	arr[i] = sc.next();
}
```
***
***
# PRINT 
```java
// First Way
for (i=0; i<num, i++){
	System.out.println(arr[i]);
}

// Second Way 
System.out.println(Arrays.toString(arr));

// Third Way
// general form - 
for (datatype var_name/ref_var : array_name)
// ------------------------------------------------------
for(int num:arr){
System.out.println(num);
}
```

***
***
# ARRAY AS AN PARAMETER

```Java
int[] num_array = {1,2,4,5,6,7};
arr(num_array);


public static void arr(int[]){
	arr[0] = 19;
}
```
***
***
# MULTI-DIMENSIONAL ARRAY
- 2-D Arrays are defined with 2 brackets 
```Java
// General form 
datatype[][] var_name = new  datatype[rows][col];
//--------------------------------------------------------
int[][] arr_2d = new int[3][];
```
- Number of Rows is *mandatory* to specify. Meanwhile, Number of Columns are not necessary to specify *because the number of col can contain "n" number of values* 
- If used **`arr.length`**; it'll return *Number of Rows*.
***
# INPUT
## 1. Hard Coded
```Java
int [][] arr = {
	{1,2},
	{3,4,5,6},
	{7,8,9}
};
System.out.print(arr[0][1]);
// Prints 2
System.out.print(arr[2])
// Prints {7,8,9,0}
```
## 2. User - Input
```Java
Scanner input = new Scanner(System.in);
int[][] arr = new int[3][2];

for(row=0; row<arr.lenght; row++){
	for(col = 0; col<arr[row].lenght; col++){
		arr[row][col] = input.nextInt();
	}
}
```

***
# OUTPUT
```Java
// First way
for(row=0; row<arr.lenght; row++){
	for(col = 0; col<arr[row].lenght; col++){
		System.out.print(arr[row][col]);
	}
}

//Second Way
for(row=0; row<arr.lenght; row++){
	System.out.println(Arrays.toString(arr[row]));
}

// Third Way
// Since 2D arrays are array of an array. Therefore using "int[]" as an datatype. 
for(int[] arr_en : arr){
System.out.print(Array.toString(arr_en))
}
```