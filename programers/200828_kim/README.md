# 서울에서 김서방 찾기

https://programmers.co.kr/learn/courses/30/lessons/12919

### 문제 설명

String형 배열 seoul의 element중 Kim의 위치 x를 찾아, 김서방은 x에 있다는 String을 반환하는 함수, solution을 완성하세요. seoul에 Kim은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

### 제한사항

- seoul은 길이 1 이상, 1000 이하인 배열입니다.
- seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.
- Kim은 반드시 seoul 안에 포함되어 있습니다.

### 문제 풀이

```jsx
function solution(seoul) {
	var answer = "";

	for (let i in seoul) {
		seoul[i] == "Kim" ? (answer = "김서방은 " + i + "에 있다") : "";
	}
	// for in 문 사용하여 배열의 index 탐색
	// for of 문을 사용하지 않은 이유는 return 값에 index가 포함되어야하기 때문
}
```
