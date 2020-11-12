# Apple and Orange

https://www.hackerrank.com/challenges/apple-and-orange/problem

### 문제 설명

You will be given two arrays of integers and asked to determine all integers that satisfy the following two conditions:

1. The elements of the first array are all factors of the integer being considered
2. The integer being considered is a factor of all elements of the second array

These numbers are referred to as being between the two arrays. You must determine how many such numbers exist.

For example, given the arrays a =[2, 6] and b = [24, 36], there are two numbers between them: 6 and 12 . 6 % 2 = 0 , 6 % 6 = 0 , 24 % 6 = 0 and 36 % 6 = 0 for the first value. Similarly 12 % 6 = 0 and 24 % 12 = 0 , 36 % 12 = 0.

Given the value of *d* for *m* apples and *n* oranges, determine how many apples and oranges will fall on Sam's house (i.e., in the inclusive range *[s, t]*)?

For example, Sam's house is between *s = 7* and *t = 10*. The apple tree is located at *a = 4* and the orange at *b = 12*. There are *m = 3* apples and *n = 3* oranges. Apples are thrown *apple = [2,3,-4]]* units distance from *a*, and *oranges = [3,-2,-4]]* units distance. Adding each apple distance to the position of the tree, they land at *[4+2,4+3,4+-4]]=[6,7,0]*. Oranges land at *[12+3,12+-2,12+-4]]=[15,10,8]*. One apple and two oranges land in the inclusive range *7-10* so we print

```
1
2
```

**Function Description**

Complete the *countApplesAndOranges* function in the editor below. It should print the number of apples and oranges that land on Sam's house, each on a separate line.

countApplesAndOranges has the following parameter(s):

- *s*: integer, starting point of Sam's house location.
- *t*: integer, ending location of Sam's house location.
- *a*: integer, location of the Apple tree.
- *b*: integer, location of the Orange tree.
- *apples*: integer array, distances at which each apple falls from the tree.
- *oranges*: integer array, distances at which each orange falls from the tree.

**Input Format**

The first line contains two space-separated integers denoting the respective values of *s* and *t*.
The second line contains two space-separated integers denoting the respective values of *a* and *b*.
The third line contains two space-separated integers denoting the respective values of *m* and *n*.
The fourth line contains *m* space-separated integers denoting the respective distances that each apple falls from point *a*.
The fifth line contains *n* space-separated integers denoting the respective distances that each orange falls from point *b*.

### 문제 풀이

```jsx
function countApplesAndOranges(s, t, a, b, apples, oranges) {
    let nAppleTotal = 0,
				nOrangeTotal = 0,
				temp1 = 0,
				temp2 = 0;

    while (temp1 < apples.length || temp2 < oranges.length) {
			if (apples[temp1] >= 0) {
				let nApple = a + apples[temp1];

				if (nApple >= s && nApple <= t) {
					nAppleTotal += 1
					temp1++;
				} else {
					temp1++;
				}
			} else {
					temp1++;
			}

			if (oranges[temp2] < 0) {
					let nOrange = b + oranges[temp2];

					if (nOrange >= s && nOrange <= t) {
							nOrangeTotal += 1;
							temp2++;
					} else {
							temp2++;
					}
			} else {
					temp2++;
			}
		}

	console.log(nAppleTotal);
	console.log(nOrangeTotal);

}
```
