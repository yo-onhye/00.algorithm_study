# 시저 암호

https://programmers.co.kr/learn/courses/30/lessons/12926

### 문제 설명

어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 'AB'는 1만큼 밀면 'BC'가 되고, 3만큼 밀면 'DE'가 됩니다. 'z'는 1만큼 밀면 'a'가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.

### 제한사항

- 공백은 아무리 밀어도 공백입니다.
- s는 알파벳 소문자, 대문자, 공백으로만 이루어져 있습니다.
- s의 길이는 8000이하입니다.
- n은 1 이상, 25이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(s, n) {
	var aTemp = [];
	for (let i of s) {
		let temp = i.charCodeAt();

		if (temp > 64 && temp < 91) {
			// 대문자일때
			temp + n > 90 ? aTemp.push(String.fromCharCode(temp + n - 26)) : aTemp.push(String.fromCharCode(temp + n));
		} else if (temp > 96 && temp < 123) {
			// 소문자일때
			temp + n > 122 ? aTemp.push(String.fromCharCode(temp + n - 26)) : aTemp.push(String.fromCharCode(temp + n));
		} else {
			aTemp.push(i);
		}
	}
	return aTemp.join("");
	// charCodeAt()을 이용하여 유니코드화 하여 해결
	// 대문자일때와 소문자일때를 나누어 판별
	// 알파벳 이외의 기호는 그냥 배열에 push
	// 알파벳의 유니코드 + n이 z 이상일 경우 a부터 카운트되도록 유니코드 값 재설정
}
```
