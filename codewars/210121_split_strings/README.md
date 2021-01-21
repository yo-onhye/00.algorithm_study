# Split Strings

https://www.codewars.com/kata/515de9ae9dcfc28eb6000001/train/javascript

### 문제 설명

Complete the solution so that it splits the string into pairs of two characters. If the string contains an odd number of characters then it should replace the missing second character of the final pair with an underscore ('_').

Examples:

```
solution('abc') // should return ['ab', 'c_']
solution('abcdef') // should return ['ab', 'cd', 'ef']
```

### 문제 풀이

```jsx
function solution(str){
  let aTemp = str.split(''),
      aResult = [];

  if(aTemp.length % 2 != 0) {
    aTemp.push("_");
  }

  for (let i = 0; i < aTemp.length; i += 2) {
    aResult.push(aTemp[i]+aTemp[i+1]);
  }
  return aResult;
}
```
