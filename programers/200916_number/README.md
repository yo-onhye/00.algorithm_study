# 평균 구하기

https://programmers.co.kr/learn/courses/30/lessons/12944

### 문제 설명

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

### 제한사항

- arr은 길이 1 이상, 100 이하인 배열입니다.
- arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

### 문제 풀이

```jsx
function solution(arr) {
	var answer = 0;
	for (let i of arr) {
		answer += i;
	}
	return answer / arr.length;
	// 배열의 값을 모두 더해 answer에 담는다
	// 배열의 원소 수를 answer로 나눠 평균을 구한다
}
```

# x만큼 간격이 있는 n개의 숫자

https://programmers.co.kr/learn/courses/30/lessons/12954

### 문제 설명

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

### 제한사항

- x는 -10000000 이상, 10000000 이하인 정수입니다.
- n은 1000 이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(x, n) {
	var answer = [];

	for (let i = 1; i < n + 1; i++) {
		answer.push(x * i);
	}
	return answer;
	// answer 배열에 x부터 시작해 x의 배수를 n개 넣어준다
}
```
