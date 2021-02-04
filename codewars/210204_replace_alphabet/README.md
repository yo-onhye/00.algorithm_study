# Replace With Alphabet Position

https://www.codewars.com/kata/546f922b54af40e1e90001da/train/javascript

### 문제 설명

Welcome.

In this kata you are required to, given a string, replace every letter with its position in the alphabet.

If anything in the text isn't a letter, ignore it and don't return it.

`"a" = 1`, `"b" = 2`, etc.

**Example**

```
alphabetPosition("The sunset sets at twelve o' clock.")
```

Should return `"20 8 5 19 21 14 19 5 20 19 5 20 19 1 20 20 23 5 12 22 5 15 3 12 15 3 11"` (as a string)

### 문제 풀이

```jsx
function alphabetPosition(text) {
    let aAlphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'];
    let aResult = [];

		text = text.toLowerCase();

    for (let i = 0; i < text.length; i++) {
      if (aAlphabet.indexOf(text[i]) !== -1){
        aResult.push(aAlphabet.indexOf(text[i])+1);
      }
    }
    return aResult.join(" ");
  }
```
