# 이상한 문자 만들기

https://programmers.co.kr/learn/courses/30/lessons/12930

### 문제 설명

문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

### 제한사항

- 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
- 첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

### 문제 풀이

```jsx
function solution(s) {
	let aAnswer = s.split(" ");
	for (let i in aAnswer) {
		aAnswer[i] = aAnswer[i].split("");
		aAnswer[i].forEach((el, i, arr) => {
			i % 2 === 0 ? (arr[i] = arr[i].toUpperCase()) : (arr[i] = arr[i].toLowerCase());
		});
		aAnswer[i] = aAnswer[i].join("");
	}
	return aAnswer.join(" ");
	// 공백을 기준으로 문자열을 나누어 배열에 담는다.
	// 가공한 배열을 탐색하며 문자도 배열에 담는다.
	// 배열을 탐색하며 짝/홀수 인덱스에 따라 대문자, 소문자로 대체하여 배열에 넣어준다.
	// 배열을 문자열으로 리턴한다.
}
```
