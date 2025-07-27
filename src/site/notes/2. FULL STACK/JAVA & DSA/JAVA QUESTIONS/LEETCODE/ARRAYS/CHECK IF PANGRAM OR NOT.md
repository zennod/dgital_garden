---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-questions/leetcode/arrays/check-if-pangram-or-not/","noteIcon":""}
---

- **PANGRAM** - *A String which contains every alphabet & it should occur only once.*
- We used HashSet as it doesn't contains any duplicate value.
- Then we iterate over every character & Compared HashSet size is it 26. 
```Java
public boolean checkIfPangram(String sentence) {
	HashSet<Character> pan = new HashSet<>();
	for (int i = 0; i < sentence.length() ; i++) {
		pan.add(sentence.charAt(i));
}
	return pan.size()==26;
}
```