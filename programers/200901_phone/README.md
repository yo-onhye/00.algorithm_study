# 핸드폰 번호 가리기

https://programmers.co.kr/learn/courses/30/lessons/12948

### 문제 설명

프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.

전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 `*` 으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

### 제한사항

- s는 길이 4 이상, 20이하인 문자열입니다.

### 문제 풀이

```jsx
function solution(phone_number) {
	var aTemp = phone_number.split(''),
			answer = '';

	for(var i in aTemp) {
		i > aTemp.length - 5 ?  answer += aTemp[i] : answer += '*';
	}
	return answer;
}
	// 문자열 phone_number를 배열로 저장한다.
	// 임시 배얼을 탐색하며 인덱스 번호가 배열의 길이-5보다 이하일 경우 '*' 문자열을 출력하고 이상일 경우 원래 숫자를 출력한다.
}
```
