# 정수 내림차순으로 배치하기

https://programmers.co.kr/learn/courses/30/lessons/12933

### 문제 설명

함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.

### 제한사항

- n은 1이상 8000000000 이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(n) {
	let aTemp = String(n).split("");

	aTemp.sort().reverse();

	return Number(aTemp.join(""));
	// 입력받은 수를 문자로 변환하여 배열 생성
	// 배열을 역순으로 정렬
	// 배열을 문자열로 변환하고 숫자형으로 바꾸어 리턴
}
```

---

# 짝수와 홀수

https://programmers.co.kr/learn/courses/30/lessons/12937

### 문제 설명

정수 num이 짝수일 경우 Even을 반환하고 홀수인 경우 Odd를 반환하는 함수, solution을 완성해주세요.

### 제한사항

- num은 int 범위의 정수입니다.
- 0은 짝수입니다.

### 문제 풀이

```jsx
function solution(num) {
	return num % 2 === 0 ? "Even" : "Odd";
}
```
