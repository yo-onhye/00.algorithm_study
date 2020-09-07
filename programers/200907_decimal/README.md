# 소수 찾기

https://programmers.co.kr/learn/courses/30/lessons/12921

### 문제 설명

1부터 입력받은 숫자 n 사이에 있는 소수의 개수를 반환하는 함수, solution을 만들어 보세요.

소수는 1과 자기 자신으로만 나누어지는 수를 의미합니다.(1은 소수가 아닙니다.)

### 제한사항

- n은 2이상 1000000이하의 자연수입니다.

### 문제 풀이

```jsx
function solution(n) {
	var i = 2,
		isPrime = true,
		result = 0;

	while (i <= n) {
		isPrime = true;
		for (var j = 2; j < i; j++) {
			if (i % j == 0) {
				isPrime = false;
				break;
			}
			continue;
		}
		isPrime == true ? result++ : "";
		i++;
	}
	return result;
	// boolean 값을 이용하여 자신과 1 이외 나누어 지는 수가 아닌 수를 카운트한다.
	// 효율성 실패..
}
```
