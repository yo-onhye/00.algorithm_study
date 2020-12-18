# Beautiful Triplets

https://www.hackerrank.com/challenges/beautiful-triplets/problem

### 문제 설명

Given a sequence of integers *a*, a triplet (*a[i], a[j], a[k]*) is beautiful if:

- *i < j < k*
- *a[j] - a[i] = a[k] - a[j] = d*

Given an increasing sequence of integers and the value of *d*, count the number of beautiful triplets in the sequence.

For example, the sequence *arr = [2, 2, 3, 4, 5]* and *d =1*. There are three beautiful triplets, by index: *[i, j, k] = [0, 2, 3], [1, 2, 3], [2, 3, 4]*. To test the first triplet, *arr[j] - arr[j] = 3 - 2 = 1* and *arr[k] - arr[j] = 4- 3 = 1*.

**Function Description**

Complete the *beautifulTriplets* function in the editor below. It must return an integer that represents the number of beautiful triplets in the sequence.

beautifulTriplets has the following parameters:

- *d*: an integer
- *arr*: an array of integers, sorted ascending

**Input Format**

The first line contains *2* space-separated integers *n* and *d*, the length of the sequence and the beautiful difference.The second line contains *n* space-separated integers *arr[j]*.

### 문제 풀이

```jsx
function beautifulTriplets(d, arr) {
    let nCount = 0;

    for(let i = 0; i < arr.length-2; i++) {
        let nVal = arr[i] + d,
            nVal2 = arr[i] + d * 2,
            nCheck = 0;
  
        for(let j = i; j < arr.length; j++) {
            if(arr[j] == nVal || arr[j] == nVal2) nCheck++;
        }
        if(nCheck == 2) nCount++;
    }
    return nCount;
}
```