# Beautiful Days at the Movies

https://www.hackerrank.com/challenges/beautiful-days-at-the-movies/problem

### 문제 설명

Lily likes to play games with integers. She has created a new game where she determines the difference between a number and its reverse. For instance, given the number **12**, its reverse is **21**. Their difference is **9**. The number **120** reversed is **21**, and their difference is **99**.

A single line of three space-separated integers describing the respective values of **i**, **j**, and **k**.

She decides to apply her game to decision making. She will look at a numbered range of days and will only go to a movie on a *beautiful day*.

Given a range of numbered days, **[i ... j]** and a number **k**, determine the number of days in the range that are *beautiful*. Beautiful numbers are defined as numbers where **[i - reverse(i)]** is evenly divisible by **k**. If a day's value is a beautiful number, it is a beautiful day. Print the number of beautiful days in the range.

**Function Description**

Complete the *beautifulDays* function in the editor below. It must return the number of beautiful days in the range.

beautifulDays has the following parameter(s):

- *i*: the starting day number
- *j*: the ending day number
- *k*: the divisor

**Input Format**
A single line of three space-separated integers describing the respective values of i, j, and k.
### 문제 풀이

```jsx
function beautifulDays(i, j, k) {
	let nCnt = 0;

	for(let x = i; x <= j; x++) {
		let nReverse = x.toString().split('').reverse().join('');
		if(Number.isInteger((x-nReverse)/k)) {
      nCnt++;
		}
	}
  return nCnt;
}
```
