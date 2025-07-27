---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/running-sum-of-1-d-array/","noteIcon":""}
---

- Here we have the **`nums`** array.
- we need the sum of every iteration *(i.e. 1, 1+2, 1+2+3)*
- So, we'll perform addition at every iteration & store it in **`sum`**.
- Lastly, we'll assign the **`sum`** value in every index of the **`runningsum[i]`** array.
```Java
int[] runningsum = new int[nums.length];  
int sum = 0;
for (int i = 0; i < nums.length ; i++) {  
    sum+=nums[i];  
    runningsum[i]=sum;  
}  
System.out.println(Arrays.toString(runningsum));
```