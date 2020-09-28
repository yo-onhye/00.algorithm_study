# 직사각형 별찍기

https://programmers.co.kr/learn/courses/30/lessons/12969

### 문제 설명

이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.별(\*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.

### 제한사항

- n과 m은 각각 1000 이하인 자연수입니다.

### 문제 풀이

```jsx
process.stdin.setEncoding("utf8");
process.stdin.on("data", (data) => {
	const aTemp = data.split(" "); // 공백에 따라 문자열을 나눔
	const n = Number(aTemp[0]),
		m = Number(aTemp[1]);
	// 입력받은 값 중 공백에 따라 첫번째로 입력받은 숫자는 n, 두번째로 입력받은 숫자는 m
	let result = "";

	for (var i = 0; i < m; i++) {
		result += "*".repeat(n) + "\n";
	}
	console.log(result);
});
```
