# 내적

https://programmers.co.kr/learn/courses/30/lessons/70128

### 문제 설명

길이가 같은 두 1차원 정수 배열 a, b가 매개변수로 주어집니다. a와 b의 [내적](https://en.wikipedia.org/wiki/Dot_product)을 return 하도록 solution 함수를 완성해주세요.

이때, a와 b의 내적은 `a[0]*b[0] + a[1]*b[1] + ... + a[n-1]*b[n-1]` 입니다. (n은 a, b의 길이)

### 제한 사항

- a, b의 길이는 1 이상 1,000 이하입니다.
- a, b의 모든 수는 -1,000 이상 1,000 이하입니다.

### 문제 풀이

```jsx
function solution(a, b) {
    var nSum = 0;

    for (let i in a) {
        nSum += (a[i]*b[i]);
    }
    return nSum;
	// 배열을 돌며 a의 i번째 인덱스 값과 b의 i번째 인덱스 값의 곱을 nSum에 더해준다.
}
```
