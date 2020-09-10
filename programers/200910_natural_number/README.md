# 자연수 뒤집어 배열로 만들기

https://programmers.co.kr/learn/courses/30/lessons/12932

### 문제 설명

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

### 제한사항

- n은 10,000,000,000이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(n) {
	var answer = [];
	for (let i of String(n)) {
		answer.push(Number(i));
	}
	return answer.reverse();
	// 자연수를 탐색하기 위해 String()을 이용하여 문자열로 변환한다.
	// 문자열을 배열로 담되, 문자열로 변환한것을 다시 Number()를 이용해 숫자로 변환한다.
	// return시 배열을 뒤집어 결과값을 반환한다.
	// split('')을 사용하여 해결하려하엿으나, 입력 받는 값이 자연수라 오류가 나서 for문으로 대체..
	// 간단하지만 타입변환 부분을 고려하지 못해 까다로웠던 문제
}
```
