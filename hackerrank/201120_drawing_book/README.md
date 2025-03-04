# Drawing Book

https://www.hackerrank.com/challenges/drawing-book/problem

### 문제 설명

A teacher asks the class to open their books to a page number. A student can either start turning pages from the front of the book or from the back of the book. They always turn pages one at a time. When they open the book, page **1** is always on the right side:

- *int p*: the page number to turn to

When they flip page **1** , they see pages **2** and **3**. Each page except the last page will always be printed on both sides. The last page may only be printed on the front, given the length of the book. If the book is **n** pages long, and a student wants to turn to page **p**, what is the minimum number of pages to turn? They can start at the beginning or the end of the book.

Given **n** and **p**, find and print the minimum number of pages that must be turned in order to arrive at page **p**.

**Example**

**n = 5**

**p = 3**

Using the diagram above, if the student wants to get to page , they open the book to page , flip  page and they are on the correct page. If they open the book to the last page, page , they turn  page and are at the correct page. Return .

**Function Description**

Complete the *pageCount* function in the editor below.

pageCount has the following parameter(s):

- *int n*: the number of pages in the book

### 문제 풀이

```jsx
function pageCount(n, p) {
	let nFrontCnt = 0, 
			nRevertCnt = 0;

	if (n === p) {
		return 0;
	}
	else if (p <= Math.floor(n / 2)) {
		for (let i = 1; i < n; i += 2) {
			if (p > i) nFrontCnt += 1;
		}
		return nFrontCnt
	} else if (p > Math.floor(n / 2)) {
		if (n % 2 != 0)  n -= 1;
		for (let j = n; j >= 0; j -= 2) {
				if (p < j) nRevertCnt += 1;
		}
		return nRevertCnt;
	}
}
```
