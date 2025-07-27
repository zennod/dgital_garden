---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/1-time-complexity/time-complexity/","noteIcon":""}
---

#DSA 

- Time complexity tells us **how the runtime of a program grows** as the *size of the input* (let’s call it `n`).

|     Notation     | Meaning              | Example                                             |
| :--------------: | -------------------- | --------------------------------------------------- |
|    **`O(1)`**    | **Constant Time**    | Accessing **`arr[i]`**, simple math                 |
|    **`O(n)`**    | **Linear Time**      | One Loop                                            |
|   **`O(n²)`**    | **Quadratic Time**   | Nested Loops                                        |
|  **`O(log n)`**  | **Logarithmic Time** | Binary Search                                       |
| **`O(n log n)`** | **Linearithmic**     | Divide and Conquer (Merge Sort, Quick Sort average) |
|   **`O(2ⁿ)`**    | **Exponential**      | Two Recursive W/O memo                              |

# FINDING TIME COMPLEXITY 
- When looking at a code snippet:
	1. **Find loops** — how many and are they nested? 
	2. **Spot recursion** — how many calls are made?
	3. **Look for divide & conquer** — is input being halved?
	4. **Ignore constants** — focus on the largest term.