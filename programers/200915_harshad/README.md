# 하샤드 수

https://programmers.co.kr/learn/courses/30/lessons/12947

### 문제 설명

양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.

### 제한사항

- `x`는 1 이상, 10000 이하인 정수입니다.

### 문제 풀이

```jsx
function solution(x) {
	var nSum = 0;
	for (let i of String(x)) {
		nSum += Number(i);
	}
	return x % nSum == 0 ? true : false;
	// 입력받은 수를 문자열로 변환하여 탐색
	// 입력받은 값의 자릿수 합을 nSum에 저장
	// x를 nSum으로 나누었을 때, 나머지 값이 0일 경우 true 아니면 false를 반환
}
```
