# Sequence Equation

https://www.hackerrank.com/challenges/permutation-equation/problem

### 문제 설명

Given a sequence of ***n*** integers, ***p(1), p(2), ... , p(n)*** where each element is distinct and satisfies ***1 ≤ p(x) ≤ n***. For each ***x*** where ***1 ≤ x ≤ n***, find any integer ***y*** such that ***p(p(y)) = x*** and print the value of on a new line.

For example, assume the sequence ***p = [5, 2, 1, 3, 4]***. Each value of ***x*** between ***1*** and ***5***, the length of the sequence, is analyzed as follows:

1. ***x = 1 = p[3],p[4] = 3,*** so ***p[p[4]] = 1***
2. ***x = 2 = p[2],p[2] = 2,*** so ***p[p[2]] = 2***
3. ***x = 3 = p[4],p[5] = 4,*** so ***p[p[5]] = 3***
4. ***x = 4 = p[5],p[1] = 5,*** so ***p[p[1]] = 4***
5. ***x = 5 = p[1],p[3] = 1,*** so ***p[p[43] = 5***

The values for ***y*** are ***[4, 2, 5, 1, 3]***.

**Function Description**

Complete the *permutationEquation* function in the editor below. It should return an array of integers that represent the values of ***y***.

permutationEquation has the following parameter(s):

- *p*: an array of integers

### 문제 풀이

```jsx
function permutationEquation(p) {
	let aTemp=[];

	for (let i = 1; i <= p.length; i++) {
		aTemp.push(p.indexOf(p.indexOf(i)+1)+1);
	}

	return aTemp;
}
```
