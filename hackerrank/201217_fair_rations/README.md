# Fair Rations

https://www.hackerrank.com/challenges/fair-rations/problem

### 문제 설명

You are the benevolent ruler of Rankhacker Castle, and today you're distributing bread. Your subjects are in a line, and some of them already have some loaves. Times are hard and your castle's food stocks are dwindling, so you must distribute *as few loaves as possible* according to the following rules:

1. Every time you give a loaf of bread to some person ***i***, you must also give a loaf of bread to the person immediately in front of or behind them in the line (i.e., persons ***i + 1*** or ***i - 1***).
2. After all the bread is distributed, each person must have an *even number* of loaves. 
Given the number of loaves already held by each citizen, find and print the minimum number of loaves you must distribute to satisfy the two rules above. If this is not possible, print `NO`.
For example, the people in line have loaves ***B = [4, 5, 6, 7]***. We can first give a loaf to ***i = 3*** and ***i = 4*** so ***B = [4, 5, 7, 8]***. Next we give a loaf to ***i = 2*** and ***i = 3*** and have ***B = [4, 6, 8, 8]*** which satisfies our conditions. We had to distribute ***4*** loaves.

**Function Description**

Complete the *fairRations* function in the editor below. It should return an integer that represents the minimum number of loaves required.

fairRations has the following parameter(s):

- *B*: an array of integers that represent the number of loaves each persons starts with

**Input Format**

The first line contains an integer ***N***, the number of subjects in the bread line.

The second line contains ***N*** space-separated integers ***B[i]***.

**Constraints**

- 2 <= N <= 1000
- 1 <= B[i] <= 10, where 1 <= i <= N

### 문제 풀이

```jsx
function fairRations(B) {
	let aTemp = [],
			nCount = 0;
	
	for(let i = 0; i < B.length-1; i++){
		aTemp.push(0);
	}

	nCount = aTemp.reduce((target, item, idx) => {
		!!(B[idx] % 2) && (B[idx + 1]++, (target += 2));
		return target;
	}, 0);

	return (B[B.length - 1] % 2) ? "NO" : nCount;
}
```