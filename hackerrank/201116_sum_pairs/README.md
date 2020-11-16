# Divisible Sum Pairs

https://www.hackerrank.com/challenges/divisible-sum-pairs/problem

### 문제 설명

You are given an array of ***n*** integers, ***ar = [ar[0], ar[1], ..., ar[n-1]]***, and a positive integer, ***k***. Find and print the number of ***(i, j)*** pairs where ***i < j*** and ***ar[i]*** +***ar[j]***  is divisible by ***k***.

- *k*: the integer to divide the pair sum by

For example, ***ar = [1, 2, 3, 4, 5, 6]*** and ***k = 5***. Our three pairs meeting the criteria are ***[1, 4], [2, 3]*** and ***[4, 6]***.

**Function Description**

Complete the *divisibleSumPairs* function in the editor below. It should return the integer count of pairs meeting the criteria.

divisibleSumPairs has the following parameter(s):

- *n*: the integer length of array *ar*
- *ar*: an array of integers


### 문제 풀이

```jsx
function divisibleSumPairs(n, k, ar) {
    let nCnt = 0;
    
    for(let i in ar) {
        for(let j in ar) {
            if(i !== j) {
                (ar[i]+ar[j])%k == 0 ? nCnt++ : '';
            }
        }
    }
    return nCnt/2;
	// 배열을 돌며 같은 인덱스가 아닌 숫자의 합이 k로 나누엇을 때 0일 경우 nCnt를 증가
	// nCnt가 i와 j 같은 케이스를 한번 더 카운트 하기때문에 nCnt를 2로 나누어 리턴
}
```
