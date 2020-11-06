# Between Two Sets

https://www.hackerrank.com/challenges/between-two-sets/problem

### 문제 설명

You will be given two arrays of integers and asked to determine all integers that satisfy the following two conditions:

1. The elements of the first array are all factors of the integer being considered
2. The integer being considered is a factor of all elements of the second array

These numbers are referred to as being between the two arrays. You must determine how many such numbers exist.

For example, given the arrays a =[2, 6] and b = [24, 36], there are two numbers between them: 6 and 12 . 6 % 2 = 0 , 6 % 6 = 0 , 24 % 6 = 0 and 36 % 6 = 0 for the first value. Similarly 12 % 6 = 0 and 24 % 12 = 0 , 36 % 12 = 0.

**Function Description**

Complete the *getTotalX* function in the editor below. It should return the number of integers that are betwen the sets.

getTotalX has the following parameter(s):

- *a*: an array of integers
- *b*: an array of integers

**Input Format**

The first line contains two space-separated integers, n, and m, the number of elements in the array a and the number of elements in the array b.

The second line contains n distinct space-separated integers describing a[i] where 0 ≤ i <n.

The third line contains distinct space-separated integers describing b[j] where 0 ≤ j < m.

### 문제 풀이

```jsx
function getTotalX(a, b) {
  let min = Math.min(...a);
  let max = Math.max(...b);
  let aResult = [];

  let divideItem = (item, index) => index % item === 0;
  let divideItemMax = (item, index) => item % index === 0;

  for (let i = min; i <= max; i++) {
    if(a.every( el => divideItem(el, i)) && b.every( el => divideItemMax(el, i))) {
        aResult.push(i);
    }
  }

  return aResult.length;
}
```
