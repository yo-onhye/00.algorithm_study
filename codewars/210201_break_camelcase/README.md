# Break camelCase

https://www.codewars.com/kata/5208f99aee097e6552000148/train/javascript

### 문제 설명

Complete the solution so that the function will break up camel casing, using a space between words.

**Example**

```
solution("camelCasing")  ==  "camel Casing
```

### 문제 풀이

```jsx
function solution(string) {
    let aString = [];

    for(let s of string) {
        if(s.match(/^[A-Z]$/) != null) { aString.push(' '); }
        aString.push(s);
    }

    return aString.join('');
}
```
