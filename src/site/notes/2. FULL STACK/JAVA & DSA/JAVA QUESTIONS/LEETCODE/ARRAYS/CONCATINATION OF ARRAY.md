---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/concatination-of-array/","noteIcon":""}
---

- **`ans[i]=nums[i]`** will add the values of **`nums[0 to 2]`** in **`ans[0 to 2]`**
- Then, **`ans[i+n]=nums[i]`**
	- **`ans[0+3]=nums[0]`** 
	- **`ans[3]=nums[0]`**; Will add the 0th index value of **`nums`** in 3rd index of the **`ans`**
```Java
int n = nums.length;  
int[] ans = new int[2*n];  
for (int i = 0; i < nums.length; i++) {  
    ans[i]=nums[i];  
    ans[i+n]=nums[i];  
}  
System.out.println(Arrays.toString(ans));
```