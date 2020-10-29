# 큰 수 만들기

https://programmers.co.kr/learn/courses/30/lessons/42883

### 문제 설명

어떤 숫자에서 k개의 수를 제거했을 때 얻을 수 있는 가장 큰 숫자를 구하려 합니다.

예를 들어, 숫자 1924에서 수 두 개를 제거하면 [19, 12, 14, 92, 94, 24] 를 만들 수 있습니다. 이 중 가장 큰 숫자는 94 입니다.

문자열 형식으로 숫자 number와 제거할 수의 개수 k가 solution 함수의 매개변수로 주어집니다. number에서 k 개의 수를 제거했을 때 만들 수 있는 수 중 가장 큰 숫자를 문자열 형태로 return 하도록 solution 함수를 완성하세요.

### 제한사항

- number는 1자리 이상, 1,000,000자리 이하인 숫자입니다.
- k는 1 이상 `number의 자릿수` 미만인 자연수입니다.

### 문제 풀이

```jsx
function solution(number, k) {
    var aTemp = [];
    for (let i of number) { 
        while (k > 0 && aTemp[aTemp.length - 1] < i) {
            aTemp.pop();
            k--;
        }
        aTemp.push(i);
    }

    aTemp.splice(aTemp.length - k, k);
    
    return aTemp.join('');
    // 입력받은 수를 돌며 이전 인덱스 숫자와 현재 숫자를 비교하여 현재 인덱스가 크면 배열에서 요소를 제거
    // 제거 한 후 제거할 수인 k를 감소
    // k가 0 이상일 경우 뒤에서 k만큼 제거
}
```
