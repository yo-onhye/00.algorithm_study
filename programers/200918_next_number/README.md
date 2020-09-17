# 다음 큰 숫자

https://programmers.co.kr/learn/courses/30/lessons/12911

### 문제 설명

자연수 n이 주어졌을 때, n의 다음 큰 숫자는 다음과 같이 정의 합니다.

- 조건 1. n의 다음 큰 숫자는 n보다 큰 자연수 입니다.
- 조건 2. n의 다음 큰 숫자와 n은 2진수로 변환했을 때 1의 갯수가 같습니다.
- 조건 3. n의 다음 큰 숫자는 조건 1, 2를 만족하는 수 중 가장 작은 수 입니다.

예를 들어서 78(1001110)의 다음 큰 숫자는 83(1010011)입니다.

자연수 n이 매개변수로 주어질 때, n의 다음 큰 숫자를 return 하는 solution 함수를 완성해주세요.

### 제한사항

- n은 1,000,000 이하의 자연수 입니다.

### 문제 풀이

```jsx
function solution(n) {
	let nAnswer = n + 1,
		nBinary = n.toString(2),
		nCount = checkOne(nBinary);

	function checkOne(i) {
		let nOne = 0;
		for (let j of String(i)) {
			if (j == "1") {
				nOne++;
			}
		}
		return nOne;
	}
	while (checkOne(nAnswer.toString(2)) !== nCount) {
		nAnswer++;
	}
	// 입력받은 값의 다음 수 부터 탐색하기위해 nAnswer 값 지정
	// n의 2진수 값을 저장하는 nBinary 생성 (없어도 될 듯)
	// n의 2진수 1의 갯수를 저장하는 nCount 생성
	// checkOne 함수를 통해 2진수의 1갯수를 반환
	// while문을 이용하여 1의 갯수가 같은 수를 찾을 때까지 nAnswer의 값을 증가
	return nAnswer;
}
```
