# 정수 제곱근 판별

https://programmers.co.kr/learn/courses/30/lessons/12934

### 문제 설명

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.

n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

### 제한사항

- n은 1이상, 50000000000000 이하인 양의 정수입니다.

### 문제 풀이

```jsx
function solution(n) {
	var nTemp = Math.sqrt(n);

	if (Number.isInteger(nTemp)) {
		return (nTemp + 1) * (nTemp + 1);
	} else {
		return -1;
	}
	// nTemp에 입력받은 n의 제곱값을 저장
	// nTemp 값이 정수 일 경우 nTemp+1을 두 번 곱하여 반환
	// 아닐 경우 -1을 반환
}
```
