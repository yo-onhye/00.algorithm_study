# Plus Minus

https://www.hackerrank.com/challenges/plus-minus/problem

### 문제 설명

Given an array of integers, calculate the ratios of its elements that are *positive*, *negative*, and *zero*. Print the decimal value of each fraction on a new line with  places after the decimal.

**Note:** This challenge introduces precision problems. The test cases are scaled to six decimal places, though answers with absolute error of up to  are acceptable.

**Example**

There are  elements, two positive, two negative and one zero. Their ratios are ,  and . Results are printed as:

```
0.400000
0.400000
0.200000
```

**Function Description**

Complete the *plusMinus* function in the editor below.

plusMinus has the following parameter(s):

- _int arr[n]_: an array of integers

**Print**Print the ratios of positive, negative and zero values in the array. Each value should be printed on a separate line with  digits after the decimal. The function should not return a value.

**Input Format**

The first line contains an integer, , the size of the array.The second line contains  space-separated integers that describe .

### 문제 풀이

```jsx
function plusMinus(arr) {
	let positive = 0;
	let negative = 0;
	let zero = 0;

	for (let i in arr) {
		if (arr[i] > 0) {
			positive++;
		} else if (arr[i] == 0) {
			zero++;
		} else {
			negative++;
		}
	}

	console.log((positive / arr.length).toFixed(6));
	console.log((negative / arr.length).toFixed(6));
	console.log((zero / arr.length).toFixed(6));
	// 배열을 돌며 원소를 유형에 맞추어 카운트
	// 배열의 원소 갯수만큼 나누어 확률을 구한 후 6자리 소수점 반올림 실행
	// 3개 값을 개행하여 return하려고 하였는데, 그냥 console.log로 출력하면 되는것이었다.
}
```
