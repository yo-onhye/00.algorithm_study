# WeIrD StRiNg CaSe

https://www.codewars.com/kata/52b757663a95b11b3d00062d/train/javascript

### 문제 설명

Write a function `toWeirdCase` (`weirdcase` in Ruby) that accepts a string, and returns the same string with all even indexed characters in each word upper cased, and all odd indexed characters in each word lower cased. The indexing just explained is zero based, so the zero-ith index is even, therefore that character should be upper cased.

The passed in string will only consist of alphabetical characters and spaces(`' '`). Spaces will only be present if there are multiple words. Words will be separated by a single space(`' '`).

### **Examples:**

```
toWeirdCase( "String" );//=> returns "StRiNg"
toWeirdCase( "Weird string case" );//=> returns "WeIrD StRiNg CaSe"
```

### 문제 풀이

```jsx
function toWeirdCase(string){
  let aWords = string.split(" "),
			nResult = '';

	for(let i in aWords) {
    if(i != 0) { nResult += ' '; }
		for(let j = 0; j < aWords[i].length; j++) {
			j % 2 === 0 ? nResult += aWords[i][j].toUpperCase() : nResult  += aWords[i][j].toLowerCase();
		}
		
	}
	return nResult;
}
```
