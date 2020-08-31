# 모의고사

https://programmers.co.kr/learn/courses/30/lessons/42840

### 문제 설명

수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.

1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, 2, 1, 2, 3, 2, 4, 2, 5, ...3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, ...

1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.

### 제한사항

- 시험은 최대 10,000 문제로 구성되어있습니다.
- 문제의 정답은 1, 2, 3, 4, 5중 하나입니다.
- 가장 높은 점수를 받은 사람이 여럿일 경우, return하는 값을 오름차순 정렬해주세요.

### 문제 풀이

```jsx
function solution(answers) {
	var aStudents = [
			[1, 2, 3, 4, 5],
			[2, 1, 2, 3, 2, 4, 2, 5],
			[3, 3, 1, 1, 2, 2, 4, 4, 5, 5],
		],
		aCount = [0, 0, 0],
		result = [];

	for (let i = 0; i < answers.length; i++) {
		if (aStudents[0][i % aStudents[0].length] === answers[i]) {
			aCount[0]++;
		}

		if (aStudents[1][i % aStudents[1].length] === answers[i]) {
			aCount[1]++;
		}

		if (aStudents[2][i % aStudents[2].length] === answers[i]) {
			aCount[2]++;
		}
	}

	let max = Math.max(...aCount);

	for (let j = 0; j < aCount.length; j++) {
		if (aCount[j] === max) {
			result.push(j + 1);
		}
	}

	return result;
	// aStudents에 학생들의 답변을 담아둔다
	// for문으로 학생들의 답변과 정답을 비교하여 정답의 수를 count 한다
	// Math.max()를 이용해 시험자 중 최고점을 구한다
	// 결과 배열을 돌며 최고점인 학생을 결과 값으로 리턴한다
}
```
