# Equalize the Array

https://www.hackerrank.com/challenges/equality-in-a-array/problem

### 문제 설명

Karl has an array of integers. He wants to reduce the array until all remaining elements are equal. Determine the minimum number of elements to delete to reach his goal.

For example, if his array is **arr = [1, 2, 2, 3]**, we see that he can delete the **2** elements **1** and  leaving **arr = [2, 2]**. He could also delete both twos and either the **1** or the **3**, but that would take **3** deletions. The minimum number of deletions is **2**.

**Function Description**

Complete the *equalizeArray* function in the editor below. It must return an integer that denotes the minimum number of deletions required.

equalizeArray has the following parameter(s):

- *arr*: an array of integers

**Input Format**

The first line contains an integer **n**, the number of elements in **arr**.The next line contains **n** space-separated integers **arr[i]**.

### 문제 풀이

```jsx
function equalizeArray(arr) {
  let oCount = {},
      nCount = 0,
      nLength = arr.length;

  for (let i in arr) {
    oCount[arr[i]] = oCount[arr[i]] + 1 || 1;
  }

  for (let val in oCount) {
      if (oCount[val] > nCount) nCount = oCount[val];
  }

  return nLength - nCount;
}
```
