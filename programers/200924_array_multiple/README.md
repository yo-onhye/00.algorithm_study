# 행렬의 곱셈

https://programmers.co.kr/learn/courses/30/lessons/12949

### 문제 설명

2차원 행렬 arr1과 arr2를 입력받아, arr1에 arr2를 곱한 결과를 반환하는 함수, solution을 완성해주세요.

### 제한사항

- 행렬 arr1, arr2의 행과 열의 길이는 2 이상 100 이하입니다.
- 행렬 arr1, arr2의 원소는 -10 이상 20 이하인 자연수입니다.
- 곱할 수 있는 배열만 주어집니다.

### 문제 풀이

```jsx
function solution(arr1, arr2) {
	var aTemp = [],
		nSum = 0;

	for (let i in arr1) {
		aTemp[i] = [];
		for (let j = 0; j < arr2[0].length; j++) {
			for (let l in arr2) {
				nSum = nSum + arr1[i][l] * arr2[l][j];
			}
			aTemp[i].push(nSum);
			nSum = 0;
		}
	}
	return aTemp;
	// aTemp 안에 arr1안의 배열만큼 빈 배열 생성
	// arr2 내부 배열의 원소를 돌며, arr1의 값과 arr2의 한 배열의 원소들의 곱한 합을 새로운 aTemp에 추가
	// arr1 내부 배열에 값을 다 저장 후, 다음 내부 배열에도 같은 방식으로 곱한 합을 추가
	// 곱한 결과를 추가한 aTemp를 반환
}
```
