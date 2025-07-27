---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/numbes-with-even-digit/","noteIcon":""}
---

- Here we need to find the digit of an number whether the number has  even digits or odd digits.
```Java
public int findNumbers(int[] nums) {
	int count = 0;
	for(int i = 0; i<nums.length; i++){
		if((int) (Math.log10(nums[i])+1) %2 == 0){
			count++;
		}
	}
	return count;
}
```