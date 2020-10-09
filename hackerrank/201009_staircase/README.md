# Staircase

https://www.hackerrank.com/challenges/staircase/problem

### 문제 설명

Staircase detail

This is a staircase of size _n = 4_ :

```
   #
  ##
 ###
####
```

Its base and height are both equal to _n_. It is drawn using `#` symbols and spaces. *The last line is not preceded by any spaces.*

Write a program that prints a staircase of size *n*.

**Function Description**

Complete the *staircase* function in the editor below.

staircase has the following parameter(s):

- _int n_: an integer

**Print**

Print a staircase as described above.

**Input Format**

A single integer, , denoting the size of the staircase.

### 문제 풀이

```jsx
function staircase(n) {
	let str = [];

	for (let i = 1; i <= n; i++) {
		for (let j = 0; j < n - i; j++) {
			str.push(" ");
		}
		for (let k = 0; k < i; k++) {
			str.push("#");
		}
		console.log(str.join(""));
		str = [];
	}
	// n층 만큼 행을 만들기 위해 for문 실행
	// 계단의 요소를 1부터 시작하되 역순으로 출력해야하기 때문에 n-i만큼 공백을 배열에 추가
	// i만큼 '#'추가하여 문자열로 만들어 매 층마다 출력
}
```
