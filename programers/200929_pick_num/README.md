# 두 개 뽑아서 더하기

https://programmers.co.kr/learn/courses/30/lessons/68644

### 문제 설명

정수 배열 numbers가 주어집니다. numbers에서 서로 다른 인덱스에 있는 두 개의 수를 뽑아 더해서 만들 수 있는 모든 수를 배열에 오름차순으로 담아 return 하도록 solution 함수를 완성해주세요.

### 제한사항

- numbers의 길이는 2 이상 100 이하입니다.
- numbers의 모든 수는 0 이상 100 이하입니다.

### 문제 풀이

```jsx
function solution(numbers) {
	let aSum = [];

	for (let i in numbers) {
		for (let j in numbers) {
			i !== j ? aSum.push(numbers[i] + numbers[j]) : "";
		}
	}

	let aUniq = aSum
		.slice()
		.sort(function (a, b) {
			return a - b;
		})
		.reduce(function (a, b) {
			if (a.slice(-1)[0] !== b) a.push(b);
			return a;
		}, []);

	return aUniq;
	// aSum에 인덱스가 같지 않을 경우 수의 합을 추가
	// aSum 배열을 복사하여 aUniq 배열을 만들고 정렬
	// 배열을 탐색하며 앞 인덱스의 값과 비교하여 배열 생성
	// 중복 값이 없이 정렬된 aUniq 배열을 리턴
}
```
