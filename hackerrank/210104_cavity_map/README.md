# Cavity Map

https://www.hackerrank.com/challenges/extra-long-factorials/problem

### 문제 설명

You are given a square map as a matrix of integer strings. Each cell of the map has a value denoting its depth. We will call a cell of the map a *cavity* if and only if this cell is not on the border of the map and each cell adjacent to it has *strictly smaller depth*. Two cells are adjacent if they have a common side, or *edge*.

Find all the cavities on the map and replace their depths with the uppercase character **X**.

**Example**

*grid = ['989', '191', '111']*

The grid is rearranged for clarity:

> 989
> 191
> 111

Return:

> 989
> 1X1
> 111

The center cell was deeper than those on its edges: *[8,1,1,1]*. The deep cells in the top two corners do not share an edge with the center cell, and none of the border cells is eligible.

**Function Description**

Complete the *cavityMap* function in the editor below.

cavityMap has the following parameter(s):

- *string grid[n]:* each string represents a row of the grid

**Returns**

- *string{n}:* the modified grid

**Input Format**

The first line contains an integer *n*, the number of rows and columns in the grid.

Each of the following *n* lines (*rows*) contains *n* positive digits without spaces (*columns*) that represent the depth at *grid[row, column]*.

### 문제 풀이

```jsx
function cavityMap(grid) {
    let oTemp = grid.map(el => el.split(''));

    for(let col = 1; col < oTemp.length - 1; col++) {
        for(let row = 1; row < oTemp[col].length - 1; row++) {
            if(oTemp[col][row] > oTemp[col][row - 1] && oTemp[col][row] > oTemp[col][row + 1] && oTemp[col][row] > oTemp[col - 1][row] && oTemp[col][row] > oTemp[col + 1][row]) {
              oTemp[col][row] = 'X'; 
            }
        }
    }

    return oTemp.map(el => el.join(''));
}
```
