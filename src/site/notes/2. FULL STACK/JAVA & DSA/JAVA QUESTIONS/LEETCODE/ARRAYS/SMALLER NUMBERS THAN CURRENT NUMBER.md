---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/smaller-numbers-than-current-number/","noteIcon":""}
---

#leetcode

- We added an **counter** which will increase as the condition satisfies.
- And that many **number of counter** will our *smaller number* than the current number.
- Lastly, Added the **`count`** to the **`[i]th`** iteration.
 ```Java
public int[] smallerNumbersThanCurrent(int[] nums) {

int[] outArr = new int[nums.length];
for(int i=0; i<nums.length; i++){
	int count = 0;
	for(int j=0; j<nums.length;j++){
		if(nums[i]>nums[j]){
			count++;
		}
	}
	outArr[i]=count;
}
return outArr;
}
```