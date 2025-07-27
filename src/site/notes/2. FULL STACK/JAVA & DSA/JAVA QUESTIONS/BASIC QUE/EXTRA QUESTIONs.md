---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/basic-que/extra-questio-ns/","noteIcon":""}
---

```Java
public static ArrayList reverseArr(int[] arr){
	ArrayList<Integer> al = new ArrayList<>(); 
	for(int i=arr.length-1; i>=0; i--){
		al.add(arr[i]);
	}
	return al;
}

public static boolean paliArr(int[] arr){
	int left = 0;
	int right = arr.length-1;
	
	while(left < right){
		if(arr[left]!= arr[right]){
			return false;
		}
		left++;
		right--;
	}
	return true;
}

public static Map eleCount(int[] arr){
	Map<Integer, Integer> hm = new HashMap<>();
	for(int i: arr){
		hm.put(i, hm.getOrDefault(i,0)+1);
	}
	return hm;
}
```