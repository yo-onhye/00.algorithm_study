# 제일 작은 수 제거하기

https://programmers.co.kr/learn/courses/30/lessons/12935

### 문제 설명

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

### 제한사항

- arr은 길이 1 이상인 배열입니다.
- 인덱스 i, j에 대해 i ≠ j이면 arr[i] ≠ arr[j] 입니다.

### 문제 풀이

```jsx
function solution(arr) {
	var aResult = arr,
		nTemp = 0;

	if (arr.length > 1) {
		nTemp = arr[0];
		for (let i of aResult) {
			nTemp > i ? (nTemp = i) : "";
		}
		aResult.splice(aResult.indexOf(nTemp), 1);
		return aResult;
	} else {
		return [-1];
	}
	// 배열의 원소가 하나 이상일 경우 작은 수를 제거하는 로직 실행
	// nTemp값에 배열의 첫번째 원소를 담고 이외 배열 요소들을 탐색하며 비교하여 작은 수를 업데이트
	// 배열을 모두 탐색 후 가장 작은 수를 배열에서 제거하여 리턴
	// 배열의 요소가 하나일 경우 [-1]을 리턴
}
```
