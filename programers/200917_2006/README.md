# 2016년

https://programmers.co.kr/learn/courses/30/lessons/12901

### 문제 설명

2016년 1월 1일은 금요일입니다. 2016년 a월 b일은 무슨 요일일까요? 두 수 a ,b를 입력받아 2016년 a월 b일이 무슨 요일인지 리턴하는 함수, solution을 완성하세요. 요일의 이름은 일요일부터 토요일까지 각각 `SUN,MON,TUE,WED,THU,FRI,SAT` 입니다. 예를 들어 a=5, b=24라면 5월 24일은 화요일이므로 문자열 TUE를 반환하세요.

### 제한사항

- 2016년은 윤년입니다.
- 2016년 a월 b일은 실제로 있는 날입니다. (13월 26일이나 2월 45일같은 날짜는 주어지지 않습니다)

### 문제 풀이

```jsx
function solution(a, b) {
	var nDay = b,
		aTemp = ["THU", "FRI", "SAT", "SUN", "MON", "TUE", "WED"];

	for (let i = 1; i < a; i++) {
		if (i === 2) {
			nDay += 29;
		} else if (i % 2 === 0 && i !== 2) {
			nDay += 30;
		} else {
			nDay += 31;
		}
	}
	return aTemp[nDay % 7];
	// aTemp에 요일을 담고, 1월 1일부터 현재 날짜까지 일자를 합하여 nDay에 담는다.
	// nDay를 7로 나누어 나머지에 해당하는 aTemp의 인덱스 값을 리턴한다.
	// test case 13번 오류
}
```

```jsx
function solution(a, b) {
	let aTemp = ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"];
	const nDate = new Date(`2016,${a},${b}`);
	return aTemp[nDate.getDay()];
	// 위와 같이 aTemp에 요일을 담고, Date()와 getDay()를 이용하여 요일을 구한다.
	// 실제로 있는 날이라서 가능했다.
}
```
