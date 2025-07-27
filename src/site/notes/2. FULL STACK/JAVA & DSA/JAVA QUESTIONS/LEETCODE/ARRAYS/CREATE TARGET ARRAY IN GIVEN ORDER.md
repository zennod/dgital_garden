---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/create-target-array-in-given-order/","noteIcon":""}
---

#leetcode 
- Here we only need to replace the values of **`nums[i]`** at index of **`index[i]`** in the new array.
```Java
public int[] createTargetArray(int[] nums, int[] index) {
ArrayList <Integer> arr = new ArrayList();
for(int i = 0; i< index.length; i++){
	arr.add(index[i],nums[i]);
}
int[] target = new int[index.length];
for(int j = 0; j < index.length; j++){
	target[j] = arr.get(j);
}
return target;
}
```