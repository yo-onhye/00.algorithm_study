# Picking Numbers

https://www.hackerrank.com/challenges/picking-numbers/problem

### 문제 설명

Given an array of integers, find the longest subarray where the absolute difference between any two elements is less than or equal to **1**.

**Example**

**a = [1, 1, 2, 2, 4, 4, 5, 5, 5]**

There are two subarrays meeting the criterion: **[1, 1, 2, 2]** and **[4, 4, 5, 5, 5]**. The maximum length subarray has **5** elements.

**Function Description**

Complete the *pickingNumbers* function in the editor below.

pickingNumbers has the following parameter(s):

- int a[n]: an array of integers

**Returns**

- int: the length of the longest subarray that meets the criterion

**Input Format**

The first line contains a single integer **n**, the size of the array

**a**. The second line contains **n** space-separated integers, each an **a[i]**.
### 문제 풀이

```jsx
function pickingNumbers(a) {
	let aTemp = new Set();
	let nMax = 0;
	for(let i of a) {
		var nCnt = 0;

		if(!aTemp.has(i)){
			aTemp.add(i);
			for(let j of a){
				if(j==i || j==i+1){
					nCnt++;
				}
			}
			nMax= Math.max(nMax,nCnt);
		}
	}
	return nMax;
}
```
