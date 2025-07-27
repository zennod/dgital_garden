---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/count-items-matching-a-rule/","noteIcon":""}
---

![Pasted image 20230909120659.png](/img/user/_resources/Pasted%20image%2020230909120659.png)

```Java
public int countMatches(List<List<String>> items, String ruleKey, String ruleValue) {
int count = 0, id = 0;
	if(ruleKey.equals("type")){
		id = 1; }
	else if (ruleKey.equals("color")){
		 id = 2; }
	else {
		id = 3;
	}

	for (int i = 0; i<items.size(); i++){
		if(items.get(i).get(id - 1).equals(ruleValue)){
			count++;
		}
	}
	return count++;
}
```