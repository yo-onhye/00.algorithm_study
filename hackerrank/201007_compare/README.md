# Compare the Triplets

https://www.hackerrank.com/challenges/compare-the-triplets/problem

### 문제 설명

Alice and Bob each created one problem for HackerRank. A reviewer rates the two challenges, awarding points on a scale from *1* to *100* for three categories: *problem clarity*, *originality*, and *difficulty*.

The rating for Alice's challenge is the triplet *a = (a[0], a[1], a[2])*, and the rating for Bob's challenge is the triplet *b = (b[0], b[1], b[2])*.

The task is to find their *comparison points* by comparing *a[0]* with *b[0]*, *a[1]* with *b[1]*, and *a[2]* with *b[2]*.

- If *a[i] > b[i]*, then Alice is awarded *1* point.
- If *a[i] < b[i]*, then Bob is awarded *1* point.
- If *a[i] = b[i]*, then neither person receives a point.

Comparison points is the total points a person earned.

Given *a* and *b*, determine their respective comparison points.

### 문제 풀이

```jsx
function compareTriplets(a, b) {
	var answer = [],
		nAwin = 0,
		nBwin = 0;

	for (var i = 0; i < a.length; i++) {
		if (a[i] > b[i]) {
			nAwin++;
		} else if (a[i] < b[i]) {
			nBwin++;
		}
	}

	answer.push(nAwin);
	answer.push(nBwin);
	return answer;
	// 답을 리턴할 빈 배열을 만들고 A,B의 이길 경우를 카운트할 변수 생성
	// a의 배열을 탐색하며 a와 b의 같은 인덱스일때 배열 요소의 값을 비교하여 승리를 카운트
	// 승리를 카운트한 값을 배열에 넣어 리턴
}
```
