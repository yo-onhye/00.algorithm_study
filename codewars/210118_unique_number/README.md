# Find the unique number

https://www.codewars.com/kata/585d7d5adb20cf33cb000235/train/javascript

### 문제 설명

There is an array with some numbers. All numbers are equal except for one. Try to find it!

```
findUniq([ 1, 1, 1, 2, 1, 1 ]) === 2
findUniq([ 0, 0, 0.55, 0, 0 ]) === 0.55
```

It’s guaranteed that array contains at least 3 numbers.

The tests contain some very huge arrays, so think about performance.

This is the first kata in series:

1. Find the unique number (this kata)
2. **[Find the unique string](https://www.codewars.com/kata/585d8c8a28bc7403ea0000c3)**
3. **[Find The Unique](https://www.codewars.com/kata/5862e0db4f7ab47bed0000e5)**

### 문제 풀이

```jsx
function findUniq(arr) {
  let oTemp = {};

  for (let i of arr){
    oTemp[i] = (oTemp[i] || 0) + 1;
  }

  for (let i in oTemp) {
    if (oTemp[i] === 1) {
      return parseFloat(i);
    }
  }
}
```
