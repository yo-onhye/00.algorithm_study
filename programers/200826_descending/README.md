# 문자열 내림차순으로 배치하기

https://programmers.co.kr/learn/courses/30/lessons/12917

### 문제 설명

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.

s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

### 제한사항

- str은 길이 1 이상인 문자열입니다.

### 문제 풀이

```jsx
function solution(s) {
	var aTemp = s.split("");

	aTemp.sort().reverse();
	return aTemp.join("");

	// 엄청나게 간단하지만, 문자열을 배열로 받는 것 까지는 했는데,
	// 문자 정렬을 charCodeAt()으로 정렬하려다 실패
	// sort()로 문자열 정렬할 수 있는것 잊지 말기
}
```
