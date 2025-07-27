---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/shuffle-the-array/","noteIcon":""}
---

- Here, 
```Java
int[] arr = new int[nums.length];  
int count = 0;  
for (int i = 0; i < n ; i++) {  
    arr[count] = nums[i];  
    arr[count + 1] = nums[i + n];  
    count+=2;  
}  
System.out.println(Arrays.toString(arr));
```