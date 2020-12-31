# Lisa's Workbook

https://www.hackerrank.com/challenges/lisa-workbook/problem

### 문제 설명

Lisa just got a new math workbook. A workbook contains exercise problems, grouped into chapters. Lisa believes a problem to be special if its index (within a chapter) is the same as the page number where it’s located. The format of Lisa’s book is as follows:

- There are **n** chapters in Lisa’s workbook, numbered from **1** to **n**.
- The *i^th* chapter has **arr[i]** problems, numbered from **1** to **arr[i]**.
- Each page can hold up to **k** problems. Only a chapter’s last page of exercises may contain fewer than **k** problems.
- Each new chapter starts on a new page, so a page will never contain problems from more than one chapter.
- The page number indexing starts at **1**.

Given the details for Lisa’s workbook, can you count its number of special problems?

For example, Lisa’s workbook contains **arr[1] = 4** problems for chapter **1**, and **arr[2] = 2** problems for chapter **2**. Each page can hold **k = 3** problems. The first page will hold **3** problems for chapter **1**. Problem **1** is on page **1**, so it is special. Page **2** contains only Chapter **1**, Problem **4**, so no special problem is on page **2**. Chapter **2** problems start on page **3** and there are **2** problems. Since there is no problem **3** on page **3**, there is no special problem on that page either. There is **1** special problem in her workbook.

**Note**: See the diagram in the Explanation section for more details.

**Function Description**

Complete the *workbook* function in the editor below. It should return an integer that represents the number of special problems in the workbook.

workbook has the following parameter(s):

- *n*: an integer that denotes the number of chapters
- *k*: an integer that denotes the maximum number of problems per page
- *arr*: an array of integers that denote the number of problems in each chapter

**Input Format**

The first line contains two integers **n** and **k**, the number of chapters and the maximum number of problems per page.The second line contains **n** space-separated integers **arr[i]** where **arr[i]** denotes the number of problems in the  *i^th* chapter.

### 문제 풀이

```jsx
function workbook(n, k, arr) {
  let nResult = 0,
			nPage = 1;

  for (let i in arr) {
    let nProblem = arr[i],
				aTemp = [];

    for (let j = 1; j <= nProblem; j++) {
        aTemp.push(j);
    }

    for (let z of aTemp) {
        z === nPage && nResult++;
        z !== nProblem && !(z % k) && nPage++;
    }
    nPage++;
  }

  return nResult;
}
```
