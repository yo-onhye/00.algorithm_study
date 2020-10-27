# 최대공약수와 최소공배수

https://programmers.co.kr/learn/courses/30/lessons/12940

### 문제 설명

두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환하는 함수, solution을 완성해 보세요. 배열의 맨 앞에 최대공약수, 그다음 최소공배수를 넣어 반환하면 됩니다. 예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12]를 반환해야 합니다.

### 제한사항

- 두 수는 1이상 1000000이하의 자연수입니다.

### 문제 풀이

```jsx
function solution(n, m) {
  let min = n,
			gcd = 1,
			lcm = 1;

	n > m ? min = m : min = n;

  for(let i = 2; i <= min; i++){
    while((n % i == 0) && (m % i == 0)) {
       n = Math.floor(n / i); 
       m = Math.floor(m / i);
       gcd = gcd * i;
       continue;
    }
  }

  lcm = n * m * gcd;

  return [gcd, lcm];
	// fot문으로 2부터 입력받은 수 중 작은 값까지 탐색하며 약수를 찾아 모두 곱하여 최대공약수를 구한다.
	// 찾은 최대공약수와 입력받은 수들을 곱하여 최소공배수를 구한다.
}
```
