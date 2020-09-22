# 행렬의 덧셈

https://programmers.co.kr/learn/courses/30/lessons/12950

### 문제 설명

행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

### 제한사항

- 행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

### 문제 풀이

```jsx
function solution(arr1, arr2) {
	var aTemp = [];

	for (let i in arr1) {
		aTemp[i] = [];
		for (let j = 0; j < arr1[0].length; j++) {
			aTemp[i][j] = arr1[i][j] + arr2[i][j];
		}
	}
	return aTemp;
	// arr1 내 배열의 수만큼 배열 생성
	// 만든 배열에 arr1과 arr2의 같은 위치에 있는 값의 합을 aTemp의 같은 위치에 추가
	// aTemp를 리턴
}
```
