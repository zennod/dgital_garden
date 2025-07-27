---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/permutation/","noteIcon":""}
---

- Make another array **`ans`** with the same length  
- Where - **`ans[i]=nums[nums[i]]`**  
- Which will calculated like this  
- If **`[0,2,1,5,3,4]`**  
- Then **`ans[1]=nums[nums[1]]`** =>
	- **`ans[1]=nums[2]`** => 
		- **`ans[1]= 1`** 
- It'll add the 2nd index value in the 1st index of **`ans[1].`**
- **`ans[] = [0,1]`**
```Java
public class Permutation {  
    public static void main(String[] args) {  
        Permutation p = new Permutation();  
    int[] arr = {0,2,1,5,3,4};  
    p.per(arr);  
    }  
  
    public void per(int[] nums) {  
       int[] ans = new int[nums.length];  
  
        for (int i = 0; i <ans.length ; i++) {  
            ans[i]=nums[nums[i]];  
        }  
        System.out.println(Arrays.toString(ans));  
    }  
}
```