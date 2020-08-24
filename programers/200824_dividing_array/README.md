# 나누어 떨어지는 숫자 배열

https://programmers.co.kr/learn/courses/30/lessons/12910

### 문제 설명

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

### 제한사항

- arr은 자연수를 담은 배열입니다.
- 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
- divisor는 자연수입니다.
- array는 길이 1 이상인 배열입니다.

### 문제 풀이

```jsx
function solution(arr, divisor) {
	var answer = [];
	for (let i of arr) {
		if (i % divisor == 0) {
			answer.push(i);
		}
	}

	answer.length === 0 ? answer.push(-1) : answer.sort((a, b) => a - b);

	return answer;
	// 배열을 탐색하여 divisor로 나누어지는 요소를 answer에 담는다.
	// answer가 빈 배열일 경우 -1을 배열에 넣고, 빈 배열이 아닐 경우 오름차순으로 정렬한다.
}
```
