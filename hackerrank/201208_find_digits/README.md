# Find Digits

https://www.hackerrank.com/challenges/find-digits/problem

### 문제 설명

An integer ***d*** is a *divisor* of an integer ***n*** if the remainder of ***n ÷ d = 0***.

Given an integer, for each digit that makes up the integer determine whether it is a divisor. Count the number of divisors occurring within the integer.

**Example**

**n = 124**

Check whether **1, 2** and **4** are divisors of **124**. All 3 numbers divide evenly into **124** so return **3**.

**n = 111**

Check whether **1, 1,** and **1** are divisors of **111**. All 3 numbers divide evenly into **111** so return **3**.

**n = 10**

Check whether **1** and **0** are divisors of **10**. **1** is, but **0** is not. Return **1**.

**Function Description**

Complete the *findDigits* function in the editor below.

findDigits has the following parameter(s):

- *int n*: the value to analyze

**Returns**

- *int:* the number of digits in **n** that are divisors of **n**

### 문제 풀이

```jsx
function findDigits(n) {
    let nDigit = 0;
    let nTemp = n.toString().split("");

  for(let item of nTemp) {
    if (n % parseInt(item) === 0) {
      nDigit++;
    }
  };
  return nDigit;
}
```
