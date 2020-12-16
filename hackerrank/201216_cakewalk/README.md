# Marc’s Cakewalk

https://www.hackerrank.com/challenges/marcs-cakewalk/problem

### 문제 설명

Marc loves cupcakes, but he also likes to stay fit. Each cupcake has a calorie count, and Marc can walk a distance to expend those calories. If Marc has eaten ***j*** cupcakes so far, after eating a cupcake with c calories he must walk at least *2i x c* miles to maintain his weight.

For example, if he eats 4 cupcakes with calorie counts in the following order: [2, 7, 8, 1], the miles he will need to walk are (20 * 2) + (21 * 7) + (22 * 8) + (23 * 1) = 2 + 14 + 32 + 8 = 56. This is not the minimum, though, so we need to test other orders of consumption. In this case, our minimum miles is calculated as (20 * 8) + (21 * 7) + (22 * 2) + (23 * 1) = 8 + 14 + 8 + 8 = 38.

Given the individual calorie counts for each of the cupcakes, determine the minimum number of miles Marc must walk to maintain his weight. Note that he can eat the cupcakes in any order.

**Input Format**

The scanner’s input string has two lines.

- The first line contains an integer *n*, the number of cupcakes in *calorie*.
- The second line contains *n* space-separated integers *calorie[i]*.

**Output Format**

Print a long integer denoting the minimum number of miles Marc must walk to maintain his weight.
### 문제 풀이

```jsx
function marcsCakewalk(calorie) {
	let aSort = calorie.sort(function(a, b) {return b - a;}),
		  nResult = 0;

  for(let i in calorie){
    nResult = nResult + ((2**i)*calorie[i]);
  }
  
  return nResult;
}
```