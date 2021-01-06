# SumFibs

https://www.codewars.com/kata/56662e268c0797cece0000bb/train/javascript

### 문제 설명

Create a function that takes an argument n and sums even fibonacci numbers upto n's index in the fibonacci sequence.

Example:

```
sumFibs(5) === 2. (0, 1, 1, 2, 3, 5); 2 is the only number in the sequence and doesn't have another number in the sequence to get added to in the indexed fibbonacci sequence.
```

Example:

```
sumFibs(9) === 44. (0, 1, 1, 2, 3, 5, 8, 13, 21, 34); 
2 + 8 + 34 = 44
```

### 문제 풀이

```jsx
function sumFibs(num) {
  let nPrev = 0,
      nCurrent = 1,
      nSum = 0;

  for (let i = 0; i < num; i++) {
    if (nCurrent % 2 == 0) {
      nSum += nCurrent;
    }
    nCurrent += nPrev;
    nPrev = nCurrent - nPrev;
  }
  return nSum;
}
```
