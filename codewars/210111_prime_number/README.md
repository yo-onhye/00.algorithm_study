# Is a number prime?

https://www.codewars.com/kata/5262119038c0985a5b00029f/train/javascript

### 문제 설명

Define a function that takes one integer argument and returns logical value `true` or `false` depending on if the integer is a prime.

Per Wikipedia, a prime number (or a prime) is a natural number greater than 1 that has no positive divisors other than 1 and itself.

## **Requirements**

- You can assume you will be given an integer input.
- You can not assume that the integer will be only positive. You may be given negative numbers as well (or `0`).
- **NOTE on performance**: There are no fancy optimizations required, but still *the* most trivial solutions might time out. Numbers go up to 2^31 (or similar, depends on language version). Looping all the way up to `n`, or `n/2`, will be too slow.

### 문제 풀이

```jsx
function isPrime(num) {
  let bResult = true;

  if (num <= 1) {
    bResult = false;
  } else if (num <= 3) {
    bResult = true;
  } else if (num % 2 == 0 || num % 3 == 0){
    bResult = false;
  }

  for (let i = 5; i * i <= num; i = i + 6) {
    if (num % i == 0 || num % (i + 2) == 0) {bResult = false;} 
  }
  return bResult; 
}
```
