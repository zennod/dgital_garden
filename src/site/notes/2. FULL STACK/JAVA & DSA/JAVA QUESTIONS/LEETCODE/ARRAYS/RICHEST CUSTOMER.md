---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/richest-customer/","noteIcon":""}
---

```Java
 int maxi=0;  
    for (int i = 0; i <arr.length; i++) {  
        int sum = 0;  
        for (int j = 0; j <arr[i].length ; j++) {  
            sum+= arr[i][j];  
        }  
        maxi = Math.max(maxi,sum);  
    }  
    System.out.println(maxi);
}
```