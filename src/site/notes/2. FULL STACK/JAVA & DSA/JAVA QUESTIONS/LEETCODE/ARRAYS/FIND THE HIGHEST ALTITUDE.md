---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/find-the-highest-altitude/","noteIcon":""}
---

- Here, we need to find the max number in the new array.
- The only condition is that the new array named **`arr[]`** should be greater than the **`gain[]`** array.
- And to find the highest altitude, we have done the SUM of the previous index of **`arr[]`** & **`gain[]`**.
```Java
public int largestAltitude(int[] gain) {
	int[] arr = new int[gain.length+1];
	arr[0]=0;
	int maxx = 0;
	for(int i = 0; i<gain.length; i++){
		arr[i+1] = gain[i]+arr[i];
		maxx = Math.max(arr[i+1], maxx);
	}
	return maxx;
}
```