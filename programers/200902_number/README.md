# 숫자의 표현

https://programmers.co.kr/learn/courses/30/lessons/12924

### 문제 설명

Finn은 요즘 수학공부에 빠져 있습니다. 수학 공부를 하던 Finn은 자연수 n을 연속한 자연수들로 표현 하는 방법이 여러개라는 사실을 알게 되었습니다. 예를들어 15는 다음과 같이 4가지로 표현 할 수 있습니다.

- 1 + 2 + 3 + 4 + 5 = 15
- 4 + 5 + 6 = 15
- 7 + 8 = 15
- 15 = 15

자연수 n이 매개변수로 주어질 때, 연속된 자연수들로 n을 표현하는 방법의 수를 return하는 solution를 완성해주세요.

### 제한사항

- n은 10,000 이하의 자연수 입니다.

### 문제 풀이

```jsx
function solution(n) {
	var answer = 0;

	for (let i = 1; i < n / 2; i++) {
		let nTotal = 1;
		for (let j = i; j <= n / 2; j++) {
			nTotal += j;
			if (nTotal === n) {
				answer++;
				break;
			} else if (nTotal > n) {
				break;
			}
		}
	}
	return answer;
	// 효율성 오류
}

function solution(n) {
	var answer = 1,
		divide = n / 2 + 1,
		nTotal = 0,
		aTemp = [];

	for (let x = 1; x <= divide; x++) {
		aTemp.push(x);
	}

	for (let i of aTemp) {
		for (let j = i; j <= divide; j++) {
			nTotal += j;
			if (nTotal === n) {
				answer++;
				break;
			} else if (nTotal > n) {
				break;
			}
		}
		nTotal = 0;
	}

	return answer;
	// 재도전.. 실패.. n/2이상부터 정답이 될 수 없다는 점을 이용하여 추가했는데도 효율성 오류가 난다.
}
```
