# 3진법 뒤집기

https://programmers.co.kr/learn/courses/30/lessons/68935

### 문제 설명

자연수 n이 매개변수로 주어집니다. n을 3진법 상에서 앞뒤로 뒤집은 후, 이를 다시 10진법으로 표현한 수를 return 하도록 solution 함수를 완성해주세요.

### 제한사항

- n은 1 이상 100,000,000 이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(n) {
  var nTemp = n.toString(3),
      aTemp = nTemp.split(''),
      answer = 0;

      aTemp.reverse();
      answer = aTemp.join('');

  
  return parseInt(answer, 3);
	// nTemp에 입력받은 값의 3진수 값을 담는다.
	// aTemp에 3진수 값을 배열로 담은 후 배열 내장객체인 reverse()를 이용하여 배열을 뒤집는다.
	// 뒤집은 배열을 문자열로 합친 후 숫자형으로 변환한다.
	// 변환한 값을 3진후로 바꾸어 리턴한다.
}
```
