# Birthday Cake Candles

https://www.hackerrank.com/challenges/birthday-cake-candles/problem

### 문제 설명

Given a square matrix, calculate the absolute difference between the sums of its diagonals.

For example, the square matrix  is shown below:

```
1 2 3
4 5 6
9 8 9
```

The left-to-right diagonal = . The right to left diagonal = . Their absolute difference is .

**Function description**

Complete the  function in the editor below.

diagonalDifference takes the following parameter:

- _int arr[n][m]_: an array of integers

**Return**

- _int_: the absolute diagonal difference

**Input Format**

The first line contains a single integer, , the number of rows and columns in the square matrix .Each of the next  lines describes a row, , and consists of  space-separated integers .

### 문제 풀이

```jsx
function diagonalDifference(arr) {
	var nSumA = 0,
		nSumB = 0;

	for (let i = 0; i < arr.length; i++) {
		for (let j = 0; j < arr.length; j++) {
			// 왼쪽위 - 오른쪽 아래 대각선에 위치한 원소의 합을 구하기 위해 행과 열의 값이 같은 값을 더한다.
			if (i === j) {
				nSumA += arr[i][j];
			}
			// 오른쪽위 - 왼쪽 아래 대각선에 위치한 원소의 합을 구하기 위해 인덱스의 합이 배열의 길이-1인 값을 더한다.
			if (i + j === arr.length - 1) {
				nSumB += arr[i][j];
			}
		}
	}

	// 절대값으로 반환
	return Math.abs(nSumA - nSumB);
}
```
