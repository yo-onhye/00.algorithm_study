# 피보나치 수

https://programmers.co.kr/learn/courses/30/lessons/12945

### 문제 설명

피보나치 수는 F(0) = 0, F(1) = 1일 때, 1 이상의 n에 대하여 F(n) = F(n-1) + F(n-2) 가 적용되는 수 입니다.

예를들어

- F(2) = F(0) + F(1) = 0 + 1 = 1
- F(3) = F(1) + F(2) = 1 + 1 = 2
- F(4) = F(2) + F(3) = 1 + 2 = 3
- F(5) = F(3) + F(4) = 2 + 3 = 5

와 같이 이어집니다.

2 이상의 n이 입력되었을 때, n번째 피보나치 수를 1234567으로 나눈 나머지를 리턴하는 함수, solution을 완성해 주세요.

### 제한사항

- n은 1이상, 100000이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(n) {
	let nAnswer = [];
	for (var i = 0; i <= n; i++) {
		if (i === 0) {
			nAnswer.push(0);
		} else if (i === 1) {
			nAnswer.push(1);
		} else {
			nAnswer.push((nAnswer[i - 1] + nAnswer[i - 2]) % 1234567);
		}
	}
	// n까지의 피보나치 수를 F(n) = F(n-1) + F(n-2)공식으로 값을 구하고 1234567로 나누어 조건에 맞는 값을 nAnswer 배열에 넣는다.
	// 이 부분을 재귀함수로 처리하니 시간 초과가 나와 for문으로 대체
	// 1과 2는 예외처리
	// n을 입력받아 배열의 n에 접근하여 값을 리턴
	return nAnswer[n];
}
```
