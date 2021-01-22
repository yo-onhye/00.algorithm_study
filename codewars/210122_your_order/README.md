# Your order, please

https://www.codewars.com/kata/515de9ae9dcfc28eb6000001/train/javascript

### 문제 설명

Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

**Examples**

```
"is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"
""  -->  ""
```
```

### 문제 풀이

```jsx
function order(words){
	let aTemp = words.split(" "),
			aResult = [];

	for(let i of aTemp) {
		aResult[i.match(/[0-9]/)-1] = i;
	}

	return aResult.join(" ");
}
```
