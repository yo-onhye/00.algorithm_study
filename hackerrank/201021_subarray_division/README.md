# Sub-array Division

https://www.hackerrank.com/challenges/the-birthday-bar/problem

### 문제 설명

Given a chocolate bar, two children, Lily and Ron, are determining how to share it. Each of the squares has an integer on it.

Lily decides to share a contiguous segment of the bar selected such that:

- The length of the segment matches Ron's birth month, and,
- The sum of the integers on the squares is equal to his birth day.

You must determine how many ways she can divide the chocolate.

Consider the chocolate bar as an array of squares, ***s = [2,2,1,3,2]***. She wants to find segments summing to Ron's birth day, ***d = 4*** with a length equalling his birth month, ***m = 2***. In this case, there are two segments meeting her criteria: ***[2,2]*** and ***[1,3]***.

**Function Description**

Complete the *birthday* function in the editor below. It should return an integer denoting the number of ways Lily can divide the chocolate bar.

birthday has the following parameter(s):

- *s*: an array of integers, the numbers on each of the squares of chocolate
- *d*: an integer, Ron's birth day
- *m*: an integer, Ron's birth month

**Input Format**

The first line contains an integer ***n***, the number of squares in the chocolate bar.The second line contains ***n*** space-separated integers ***s[i]***, the numbers on the chocolate squares where ***0 < i < n***.The third line contains two space-separated integers, ***d*** and ***m***, Ron's birth day and  his birth month.

### 문제 풀이

```jsx
function birthday(s, d, m) { 
  let nResult = 0,
      nSum = 0;

  for(let i = 0 ; i <= (s.length - m) ; i++){
      for(let j = 0 ; j < m ; j++){
          nSum = nSum + s[j+i];
      }
      if(nSum == d){
          nResult++;
      }
      nSum = 0;
  }
  return nResult;
}
```
