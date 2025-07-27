---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/matrix-diagonal-sum/","noteIcon":""}
---

- First we find the Primary Diagonal using **`mat[i][i]`**
- Then, Secondary Diagonal via **`[i][n-i-1]`**
- And lastly, Returning the **`sum`**
![Pasted image 20230913215141.png](/img/user/_resources/Pasted%20image%2020230913215141.png)
```Java
public int diagonalSum(int[][] mat) {
	int sum = 0;
	int n = mat.length;
	for(int i = 0; i<n; i++){
		sum+= mat [i][i];
		if(i != n-i-1){
			sum+= mat[i] [n-i-1];
		}
	}
	return sum;
}
```