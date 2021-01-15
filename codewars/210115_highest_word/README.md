# Highest Scoring Word

https://www.codewars.com/kata/57eb8fcdf670e99d9b000272/train/javascript

### 문제 설명

Given a string of words, you need to find the highest scoring word.

Each letter of a word scores points according to its position in the alphabet: `a = 1, b = 2, c = 3` etc.

You need to return the highest scoring word as a string.

If two words score the same, return the word that appears earliest in the original string.

All letters will be lowercase and all inputs will be valid.

### 문제 풀이

```jsx
function high(x){
	let aInput = x.split(" "),
			aVal = [],
			nTemp = 0,
			nIndex = 0,
			aLetter = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
	
	for (let i in aInput) {
		for (let j in aInput[i]) {
			nTemp += aLetter.indexOf(aInput[i].charAt(j))+1;
		}
		aVal.push(nTemp);
		nTemp = 0;
	}

	for (let i in aVal) {
		if (aVal[i] > aVal[nIndex]) { nIndex = i; }
	}
	return aInput[nIndex];
}
```
