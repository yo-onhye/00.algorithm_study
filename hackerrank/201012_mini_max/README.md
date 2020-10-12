# Mini-Max Sum

https://www.hackerrank.com/challenges/mini-max-sum/problem

### 문제 설명

Given five positive integers, find the minimum and maximum values that can be calculated by summing exactly four of the five integers. Then print the respective minimum and maximum values as a single line of two space-separated long integers.

**Example**

_arr = [1,3,5,7,9]_

The minimum sum is *1+3+5+7=16* and the maximum sum is *3+5+7+9=24*. The function prints

```
16 24
```

**Function Description**

Complete the *miniMaxSum* function in the editor below.

miniMaxSum has the following parameter(s):

- _arr_: an array of  *5* integers

**Print**

Print two space-separated integers on one line: the minimum sum and the maximum sum of *4* of *5*  elements.

**Input Format**

A single line of five space-separated integers.

**Output Format**

Print two space-separated long integers denoting the respective minimum and maximum values that can be calculated by summing exactly *four* of the five integers. (The output can be greater than a 32 bit integer.)

### 문제 풀이

```jsx
function miniMaxSum(arr) {
	let mini = 0;
	let max = 0;

	arr.sort(function (a, b) {
		return a - b;
	});

	// mini 값 구하기 위해 적은 수 부터 순차대로 합
	for (let i = 0; i < arr.length - 1; i++) {
		mini += arr[i];
	}
	// max 값 구하기 위해 제일 작은 수 다음부터 순차대로 합
	for (let j = arr.length - 1; j > 0; j--) {
		max += arr[j];
	}
	console.log(mini, max);
}
```
