# Mark and Toys

https://www.hackerrank.com/challenges/mark-and-toys/problem?h_r=internal-search

### 문제 설명

Mark and Jane are very happy after having their first child. Their son loves toys, so Mark wants to buy some. There are a number of different toys lying in front of him, tagged with their prices. Mark has only a certain amount to spend, and he wants to maximize the number of toys he buys with this money. Given a list of toy prices and an amount to spend, determine the maximum number of gifts he can buy.

**Note** Each toy can be purchased only once.

**Example**

***price = [1, 2, 3, 4]***

***k = 7***

The budget is ***7*** units of currency. He can buy items that cost ***[1, 2, 3]***  for ***6***, or ***[3, 4]*** for ***7*** units. The maximum is ***3*** items.

**Function Description**

Complete the function *maximumToys* in the editor below.

maximumToys has the following parameter(s):

- *int prices[n]:* the toy prices
- *int k:* Mark's budget

**Returns**

- *int:* the maximum number of toys

**Input Format**

The first line contains two integers, ***n*** and ***k***, the number of priced toys and the amount Mark has to spend.
### 문제 풀이

```jsx
function maximumToys(prices, k) {
	let aSort = prices.sort(function(a, b) {return a - b;}),
		  nTotal = 0;

  for (let i in aSort) {
    if (k > aSort[i]) {
      nTotal++;
      k -= aSort[i];
    } else {
      return nTotal;
    }
  }
};
```
