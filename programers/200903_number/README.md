# 문자열을 정수로 바꾸기

https://programmers.co.kr/learn/courses/30/lessons/12925

### 문제 설명

문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

### 제한사항

- s의 길이는 1 이상 5이하입니다.
- s의 맨앞에는 부호(+, -)가 올 수 있습니다.
- s는 부호와 숫자로만 이루어져있습니다.
- s는 으로 시작하지 않습니다.

### 문제 풀이

```jsx
function solution(s) {
	return parseInt(s);
	// 생각보다 간단
}
```

---

# 약수의 합

https://programmers.co.kr/learn/courses/30/lessons/12928

### 문제 설명

정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.

### 제한사항

- n은 0 이상 3000이하인 정수입니다.

### 문제 풀이

```jsx
function solution(n) {
	var answer = 0;

	for (var i = 1; i <= n; i++) {
		n % i === 0 ? (answer += i) : "";
	}

	return answer;
}
```
