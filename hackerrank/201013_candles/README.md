# Birthday Cake Candles

https://www.hackerrank.com/challenges/birthday-cake-candles/problem

### 문제 설명

You are in charge of the cake for a child's birthday. You have decided the cake will have one candle for each year of their total age. They will only be able to blow out the tallest of the candles. Count how many candles are tallest.

**Example**

_candles = [4,4,1,3]_

The maximum height candles are *4* units high. There are *2* of them, so return *2*.

**Function Description**

Complete the function `birthdayCakeCandles` in the editor below.

birthdayCakeCandles has the following parameter(s):

- _int candles[n]_: the candle heights

**Returns**

- _int_: the number of candles that are tallest

**Input Format**

The first line contains a single integer, *n*, the size of *candles[]*.The second line contains *n* space-separated integers, where each integer *i* describes the height of *candles[i]*.

### 문제 풀이

```jsx
function birthdayCakeCandles(candles) {
	let max = 0;
	let filtered;

	candles.sort(function (a, b) {
		return a - b;
	});

	// 배열 내 최대값을 max에 할당
	max = candles[candles.length - 1];

	// 배열 내 max 값에 해당하는 원소의 개수를 반환
	filtered = candles.filter(function (value, index, arr) {
		return value === max;
	});

	return filtered.length;
}
```
