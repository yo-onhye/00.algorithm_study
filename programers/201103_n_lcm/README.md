# N개의 최소공배수

https://programmers.co.kr/learn/courses/30/lessons/12953

### 문제 설명

두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다. 예를 들어 2와 7의 최소공배수는 14가 됩니다. 정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다. n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요.

### 제한사항

- arr은 길이 1이상, 15이하인 배열입니다.
- arr의 원소는 100 이하인 자연수입니다.

### 문제 풀이

```jsx
function solution(arr) {
    var answer = 0,
				lcm;

    arr.sort((a,b)=>a-b);  

		lcm = arr[0] * arr[1] / getGcd(arr[0], arr[1]);

		for (let i = 2; i < arr.length; i++) {
			lcm = lcm * arr[i] / getGcd(lcm, arr[i]);
		}
			
		return lcm;

    function getGcd (small,big){
			while (small != 0) {
					let temp = big % small;
					big = small;
					small = temp;
				}
				return big;
    }
		// 들어온 수를 오름차순으로 정렬
		// 최소공배수를 구하기 위해 순차적으로 수를 비교하여 최대공약수를 구한다.
		// 최대 공약수를 구하는 함수를 만들어 a * b / getGcd(a,b) 를 통해 각 요소를 탐색하며 배열 요소들의 최소 공배수를 구한다.
}
```
