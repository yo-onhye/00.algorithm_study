# Minimum Distances

https://www.hackerrank.com/challenges/minimum-distances/problem

### 문제 설명

The distance between two array values is the number of indices between them. Given *a*, find the minimum distance between any pair of equal elements in the array. If no such value exists, return *-1*.

**Example**

*a = [3, 2, 1, 2, 3]*

There are two matching pairs of values: *3* and *2*. The indices of the *3*'s are *i = 0* and *j = 4*, so their distance is *d[i, j] = |j i| = 4*. The indices of the *2*'s are *i = 1* and *j = 3*, so their distance is *d[i, j] = |j i| = 2*. The minimum distance is *2*.

**Function Description**

Complete the *minimumDistances* function in the editor below.

minimumDistances has the following parameter(s):

- *int a[n]:* an array of integers

**Returns**

- *int:* the minimum distance found or *-1* if there are no matching elements

**Input Format**

The first line contains an integer *n*, the size of array *a*.The second line contains *n* space-separated integers *a[i]*.

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
    return nMin == 'infinity' ? -1 : nMin;
}
```