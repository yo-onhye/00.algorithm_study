# JadenCase 문자열 만들기

https://programmers.co.kr/learn/courses/30/lessons/12951

### 문제 설명

JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.

### 제한사항

- s는 길이 1 이상인 문자열입니다.
- s는 알파벳과 공백문자(" ")로 이루어져 있습니다.
- 첫 문자가 영문이 아닐때에는 이어지는 영문은 소문자로 씁니다. ( 첫번째 입출력 예 참고 )

### 문제 풀이

```jsx
function solution(s) {
	var aTemp = s.split("");

	aTemp[0] = aTemp[0].toUpperCase();

	for (let i = 0; i < aTemp.length - 1; i++) {
		aTemp[i] == " " ? (aTemp[i + 1] = aTemp[i + 1].toUpperCase()) : (aTemp[i + 1] = aTemp[i + 1].toLowerCase());
	}
	return aTemp.join("");
	// 입력받은 문자열을 split()을 통해 배열로 저장
	// 문자열의 첫글자는 항상 대문자이니 toUpperCase()로 변환
	// 문자열 배열을 탐색하며 공백이 있을 경우 다음 문자열은 대문자로, 공백이 아닐 경우 소문자로 변환
	// 배열을 join()을 통해 문자열로 return
}
```
