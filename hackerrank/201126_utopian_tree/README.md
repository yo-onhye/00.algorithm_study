# Utopian Tree

https://www.hackerrank.com/challenges/utopian-tree/problem

### 문제 설명

The Utopian Tree goes through *2* cycles of growth every year. Each spring, it *doubles* in height. Each summer, its height increases by *1* meter.

- int: the height of the tree after the given number of cycles

A Utopian Tree sapling with a height of *1* meter is planted at the onset of spring. How tall will the tree be after **n** growth cycles?

For example, if the number of growth cycles is **n = 5**, the calculations are as follows:

> Period Height
0            1
1            2
2            3
3            6
4            7
5           14

**Function Description**

Complete the *utopianTree* function in the editor below.

utopianTree has the following parameter(s):

- *int n*: the number of growth cycles to simulate

**Returns**
- *int*: the height of the tree after the given number of cycles
### 문제 풀이

```jsx
function utopianTree(n) {
	let nHeight = 1;
	for (let i = 0; i < n; i++) {
    if (i % 2 == 0) {
      nHeight *= 2
    } else {
      nHeight++;
    }
  }
  console.log(n);    
  return nHeight;
}
```
