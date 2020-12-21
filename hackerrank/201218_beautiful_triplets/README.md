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
function minimumDistances(a) {
    let nMin = Math.pow(10,1000);
    let oTemp = {};

    for (let i = 0; i < a.length; i++){
        if (oTemp[a[i]]){
            let nGap = (i - (oTemp[a[i]] -1));

            if (nGap < nMin){
                nMin = nGap;
            }
            oTemp[a[i]] = i+1;
        } else{
            oTemp[a[i]] = i+1;
        }
    }
    return nMin == 'Infinity' ? -1 : nMin;
}
```