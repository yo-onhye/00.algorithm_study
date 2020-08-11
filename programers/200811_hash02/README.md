# 전화번호 목록

https://programmers.co.kr/learn/courses/30/lessons/42577

### **문제 설명**

수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.

마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.

전화번호부에 적힌 전화번호 중, 한 번호가 다른 번호의 접두어인 경우가 있는지 확인하려 합니다.전화번호가 다음과 같을 경우, 구조대 전화번호는 영석이의 전화번호의 접두사입니다.

- 구조대 : 119
- 박준영 : 97 674 223
- 지영석 : 11 9552 4421

전화번호부에 적힌 전화번호를 담은 배열 phone_book 이 solution 함수의 매개변수로 주어질 때, 어떤 번호가 다른 번호의 접두어인 경우가 있으면 false를 그렇지 않으면 true를 return 하도록 solution 함수를 작성해주세요.

### 제한사항

- phone_book의 길이는 1 이상 1,000,000 이하입니다.
- 각 전화번호의 길이는 1 이상 20 이하입니다.

### 문제 풀이

이번 문제는 JavaScript로 풀 수 있는 문제인데, 언어 선택지에 없어 Java로 푼 후 JavaScript로 변환했다:(

```jsx
class Solution {
    public boolean solution(String[] phone_book) {
        String sCompare = phone_book[0]; // 기준이 될 문자열
        int nCount = 0;
        
        if(phone_book.length == 1) {
            return true;
        } else {
            for(int i = 1; i < phone_book.length; i++) {
                if(phone_book[i].length() < sCompare.length()) {
                    sCompare = phone_book[i];
                }
            }
            for(int j = 0; j < phone_book.length; j++) {
                if(phone_book[j].startsWith(sCompare)) {
                    nCount++;
                }
            }
        }
        if(nCount > 1) {
            return false;
        } else {
            return true;
        }
    }
}
```


```jsx
function solution(arr) {
    var sCompare = arr[0], // 기준이 될 문자열
        nCount = 0;

    if(arr.length == 1) {
        return true;
    } else {
        for(i = 1; i < arr.length; i++) {
            arr[i].length < sCompare.length ? sCompare = arr[i] : '';
        }
        for(j = 0; j < arr.length; j++) {
            arr[j].startsWith(sCompare) ? nCount++ : '';
        }
    }

    return nCount > 1 ? false : true;
}
```