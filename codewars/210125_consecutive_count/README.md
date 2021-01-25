# Consecutive Count

https://www.codewars.com/kata/59c3e819d751df54e9000098/train/javascript

### 문제 설명

I want to know the size of the longest consecutive elements of X in Y. You will receive two arguments: `items` and `key`. Return the length of the longest segment of consecutive `keys` in the given `items`.

**Notes:**

- The items and the key will be either an integer or a string (consisting of **letters only**)
- If the key does not appear in the items, return `0`

**Examples**

```
90000, 0           -->  4
"abcdaaadse", "a"  -->  3
"abcdaaadse", "z"  -->  0
```

### 문제 풀이

```jsx
function getConsectiveItems(items, key){
    let aTemp = String(items).split(""),
        nResult = 0;
  
    key = String(key);
  
    for(let i = 0; i < aTemp.length; i++) {
      if(aTemp[i] === key) {
        let count = 1;

        for(let j = i + 1; j < aTemp.length; j++) {
          if(aTemp[j] !== key) break;
          count++;
        }
        nResult = nResult < count ? count : nResult;
      }
    }
    return nResult;
}
```
