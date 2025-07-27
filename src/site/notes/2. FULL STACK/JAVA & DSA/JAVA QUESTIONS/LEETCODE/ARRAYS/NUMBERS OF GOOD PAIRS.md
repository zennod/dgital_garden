---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/numbers-of-good-pairs/","noteIcon":""}
---

- Here, you need to find the number of pairs occurred according to the array values.
- Such as, **`arr = [1,2,3,1,1,3]`**
- Here, there are 4 Pairs; i.e. **`(0,3), (0,4), (3,4), (2,5)`** *(Indexes)*
```Java
public int numIdenticalPairs(int[] nums) {
int out = 0;
for(int i = 0; i<nums.length; i++){
	for(int j = i+1; j<nums.length; j++){
		if(nums[i]==nums[j]){
			out++;
		}
	}
}
return out;
}
```