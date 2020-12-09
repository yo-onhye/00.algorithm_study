# Cut the sticks

https://www.hackerrank.com/challenges/cut-the-sticks/problem

### 문제 설명

You are given a number of sticks of varying lengths. You will iteratively cut the sticks into smaller sticks, discarding the shortest pieces until there are none left. At each iteration you will determine the length of the shortest stick remaining, cut that length from each of the longer sticks and then discard all the pieces of that shortest length. When all the remaining sticks are the same length, they cannot be shortened so discard them.

Given the lengths of **n** sticks, print the number of sticks that are left before each iteration until there are none left.

**Example**

**arr = [1, 2, 3]**

Check whether **1, 2** and **4** are divisors of **124**. All 3 numbers divide evenly into **124** so return **3**.

**n = 111**

The shortest stick length is **1**, so cut that length from the longer two and discard the pieces of length . Now the lengths are **arr = [1, 2]**. Again, the shortest stick is of length **1**, so cut that amount from the longer stick and discard those pieces. There is only one stick left, **arr = [1]**, so discard that stick. The number of sticks at each iteration are **answer = [3, 2, 1]**.

**Function Description**

Complete the *cutTheSticks* function in the editor below. It should return an array of integers representing the number of sticks before each cut operation is performed.

cutTheSticks has the following parameter(s):

- *int arr[n]:* the lengths of each stick

**Returns**

- *int[]:* the number of sticks after each iteration

### 문제 풀이

```jsx
function cutTheSticks(arr) {
  let aSort = arr.sort(function(a, b) {return a - b;}),
      nCnt = arr.length,
      aTemp = [nCnt];

  for(let i = 1; i < arr.length; i++) {
    nCnt--;
    if(aSort[i-1] !== aSort[i]){
      aTemp.push(nCnt);
    }
  }
	return aTemp;
}
```
