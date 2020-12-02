# Repeated String

https://www.hackerrank.com/challenges/repeated-string/problem

### 문제 설명

Lilah has a string, **s**, of lowercase English letters that she repeated infinitely many times.

Given an integer, **n**, find and print the number of letter a's in the first **n** letters of Lilah's infinite string.

For example, if the string **s = 'abcac'** and **n = 10**, the substring we consider is **abcacabcac**, the first **10** characters of her infinite string. There are **4** occurrences of a in the substring.

**Function Description**

Complete the repeatedString function in the editor below. It should return an integer representing the number of occurrences of a in the prefix of length **n** in the infinitely repeating string.

repeatedString has the following parameter(s):

- s: a string to repeat
- n: the number of characters to consider

**Input Format**

The first line contains a single string, **s**.

The second line contains an integer, **n**.
### 문제 풀이

```jsx
function repeatedString(s, n) {
	let nCnt = 0;
	if(s.length == 1 && s != 'a') {
		return 0;
	} else if(s.length == 1 && s == 'a') {
		return n;
	} else if(s.length > n) {
		for(let i of s) {
			if(i == 'a') nCnt++;
		}
		return nCnt;
	} else {
		let sNew = '';

		for(let i = 0; i < parseInt(n/s.length); i++){
			sNew = sNew + s;
		}
		sNew = sNew + s.slice(0, parseInt(n%s.length));

		for(let j of sNew) {
			if(j == 'a') nCnt++;
		}
		return nCnt; 
	}
}
```
