# 문자열 다루기 기본

https://programmers.co.kr/learn/courses/30/lessons/12918

### 문제 설명

문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 예를 들어 s가 a234이면 False를 리턴하고 1234라면 True를 리턴하면 됩니다.

### 제한사항

- s는 길이 1 이상, 길이 8 이하인 문자열입니다.

### 문제 풀이

```jsx
function solution(s) {
	var aTemp = s.split(""),
		answer = true;

	if ((aTemp.length == 4) | (aTemp.length == 6)) {
		for (var i of aTemp) {
			if (i.charCodeAt() > 60) {
				answer = false;
			}
		}
	} else {
		answer = false;
	}
	return answer;
	// 문자열이 4 혹은 6글자인지 판별
	// 아스키코드를 이용해 문자열 탐색
}
```
