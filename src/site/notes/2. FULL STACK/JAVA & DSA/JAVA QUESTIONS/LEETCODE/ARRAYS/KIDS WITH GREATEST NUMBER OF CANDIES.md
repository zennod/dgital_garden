---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/kids-with-greatest-number-of-candies/","noteIcon":""}
---

- Here, we need to find the Kid with greatest number of candies.
- To do so, First you need to find out the MAXIMUM number present in the **`candies[]`** array.
- Then, if **`candies[i] + extracandies>= maximum`** *return TRUE* or *FALSE*.
```Java
public List<Boolean> kidsWithCandies(int[] candies, int extraCandies) {
int max = candies[0];
for(int i = 0; i<candies.length; i++){
	if(candies[i]>max){
		max = candies[i];
	}
}
ArrayList<Boolean> result = new ArrayList();
for(int j = 0; j<candies.length ; j++){
	result.add(candies[j]+extraCandies >= max);
}
	return result;
}
```