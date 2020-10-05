# 자릿수 더하기

https://programmers.co.kr/learn/courses/30/lessons/12931

### 문제 설명

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

### 제한사항

- N의 범위 : 100,000,000 이하의 자연수

### 문제 풀이

```jsx
function solution(n) {
	let aTemp = String(n).split(""),
		nSum = 0;

	for (let i of aTemp) {
		nSum += Number(i);
	}

	return nSum;
	// 입력받은 수를 문자로 변환하여 배열 생성
	// 배열을 탐색하며 요소들의 합을 구하여 리턴
}
```
