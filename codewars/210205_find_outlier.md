# Find The Parity Outlier

https://www.codewars.com/kata/5526fc09a1bbd946250002dc/train/javascript

### 문제 설명

You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer N. Write a method that takes the array as an argument and returns this "outlier" N.

Examples
[2, 4, 0, 100, 4, 11, 2602, 36]
Should return: 11 (the only odd number)

[160, 3, 1719, 19, 11, 13, -21]
Should return: 160 (the only even number)

### 문제 풀이

```jsx
function findOutlier(integers){
  let nCount = 0;
  for (let i in integers){
    if (integers[i] % 2 == 0){nCount++}
    else {nCount--}
  }

  for (let i in integers){
    if ((integers[i] % 2 == 0) != (nCount > 0)){
      return integers[i];
    }
  }
}
```
