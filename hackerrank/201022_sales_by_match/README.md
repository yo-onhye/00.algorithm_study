# Sales by Match

https://www.hackerrank.com/challenges/sock-merchant/problem

### 문제 설명

Alex works at a clothing store. There is a large pile of socks that must be paired by color for sale. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.

For example, there are ***n = 7*** socks with colors ***ar = [1,2,1,2,1,3,2]***. There is one pair of ***1*** color  and one of color ***2***. There are three odd socks left, one of each color. The number of pairs is ***2***.

**Function Description**

Complete the *sockMerchant* function in the editor below. It must return an integer representing the number of matching pairs of socks that are available.

sockMerchant has the following parameter(s):

- *n*: the number of socks in the pile
- *ar*: the colors of each sock

**Input Format**

The first line contains an integer ***n***, the number of socks represented in ***ar***. The second line contains ***n*** space-separated integers describing the colors ***ar[i]*** of the socks in the pile.

### 문제 풀이

```jsx
function sockMerchant(n, ar) {
    let aCopy = ar,
        result = 0;

    for (let i of ar) {
        // 현재 원소 값을 미리 배열에서 삭제
        ar.splice(ar.indexOf(i),1);
        // 비교 값을 지운 후에도 현재 원소 값과 동일한 원소가 있으면 해당 원소를 삭제하고 갯수 증가
        if(ar.indexOf(i) >= 0) {
            ar.splice(ar.indexOf(i),1);
            result++;
        } 
    }
    return result;
}
```
