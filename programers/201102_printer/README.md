# 프린터

https://programmers.co.kr/learn/courses/30/lessons/42587

### 문제 설명

예를 들어, 4개의 문서(A, B, C, D)가 순서대로 인쇄 대기목록에 있고 중요도가 2 1 3 2 라면 C D A B 순으로 인쇄하게 됩니다.

내가 인쇄를 요청한 문서가 몇 번째로 인쇄되는지 알고 싶습니다. 위의 예에서 C는 1번째로, A는 3번째로 인쇄됩니다.

현재 대기목록에 있는 문서의 중요도가 순서대로 담긴 배열 priorities와 내가 인쇄를 요청한 문서가 현재 대기목록의 어떤 위치에 있는지를 알려주는 location이 매개변수로 주어질 때, 내가 인쇄를 요청한 문서가 몇 번째로 인쇄되는지 return 하도록 solution 함수를 작성해주세요.

### 제한사항

- 현재 대기목록에는 1개 이상 100개 이하의 문서가 있습니다.
- 인쇄 작업의 중요도는 1~9로 표현하며 숫자가 클수록 중요하다는 뜻입니다.
- location은 0 이상 (현재 대기목록에 있는 작업 수 - 1) 이하의 값을 가지며 대기목록의 가장 앞에 있으면 0, 두 번째에 있으면 1로 표현합니다.

### 문제 풀이

```jsx
function solution(priorities, location) {
  let count = 0;
  let current;

  let aTemp = priorities.map((target, index) => ({
      priority: index === location,
      value: target
  }));

  while(true) {
      current = aTemp.shift() ;
      if (aTemp.some(target => target.value > current.value)) {
          aTemp.push(current);
      } else {
          count++;
          if(current.priority) return count;
      }
  }
	// aTemp에 index가 location과 같은지에 대한 여부와 우선순위값을 저장
	// aTemp에 target.value보다 큰 current.value가 존재할 경우 aTemp에 다시 넣는다.
	// 아니라면 count를 증가, 그 current가 index가 location과 같다면 count를 return
}
```
