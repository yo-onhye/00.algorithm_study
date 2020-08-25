# 수박수박수박수박수박수?

https://programmers.co.kr/learn/courses/30/lessons/12922

### 문제 설명

길이가 n이고, 수박수박수박수....와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 수박수박을 리턴하고 3이라면 수박수를 리턴하면 됩니다.

### 제한사항

- n은 길이 10,000이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(n) {
	var answer = [];

	for (let i = 0; i < n; i++) {
		i % 2 == 0 ? answer.push("수") : answer.push("박");
	}
	return answer.join("");
	// answer를 배열로 선언하고 짝수일 경우 '수', 홀수일 경우 '박'을 넣어준다.
	// return 값은 문자열로 반환되어야함으로 배열 answer를 join()을 통하여 문자열로 반환한다.
}
```
