# 최댓값과 최솟값

https://programmers.co.kr/learn/courses/30/lessons/12939

### 문제 설명

문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 "(최소값) (최대값)" 형태의 문자열을 반환하는 함수, solution을 완성하세요.

예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고, "-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.

### 제한사항

- s에는 둘 이상의 정수가 공백으로 구분되어 있습니다.

### 문제 풀이

```jsx
function solution(s) {
	var aTemp = s.split(" ");

	for (let i in aTemp) {
		aTemp[i] = Number(aTemp[i]);
	}

	aTemp.sort(function (a, b) {
		return a - b;
	});

	return String(aTemp[0]) + " " + String(aTemp[aTemp.length - 1]);

	// 입력받은 문자열을 배열로 저장
	// 배열로 저장한 값이 문자열이라 sort가 되지 않아, Number로 바꿔 다시 저장
	// 오름차순으로 배열 요소들을 저장하고 최솟값과 최댓값을 문자열로 리턴
}
```
