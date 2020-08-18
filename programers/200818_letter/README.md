# 가운데글자 가져오기

https://programmers.co.kr/learn/courses/30/lessons/12903

### 문제 설명

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

### 제한사항

- s는 길이가 1 이상, 100이하인 스트링입니다.

### 문제 풀이

```jsx
function solution(s) {
	var answer = "";
	var aArray = s.split("");
	var nLength = s.length;

	if (nLength == 1) {
		answer = s;
	} else {
		if (nLength % 2 == 0) {
			// 짝수일 경우
			answer += aArray[nLength / 2 - 1];
			answer += aArray[nLength / 2];
		} else {
			answer += aArray[parseInt(nLength / 2)];
		}
	}
	return answer;
}

// 나는 배열로 바꾸어 했는데, substring이나 charAt, slice로 많이햇다
// 굳이 배열에 넣을 필요 없을 듯
```
