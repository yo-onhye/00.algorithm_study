# Encrypt this!

https://www.codewars.com/kata/5848565e273af816fb000449/train/javascript

### 문제 설명

You want to create secret messages which can be deciphered by the **[Decipher this!](https://www.codewars.com/kata/decipher-this)** kata. Here are the conditions:

1. Your message is a string containing space separated words.
2. You need to encrypt each word in the message using the following rules:
    - The first letter needs to be converted to its ASCII code.
    - The second letter needs to be switched with the last letter
3. Keepin' it simple: There are no special characters in input.

**Examples:**

```
encryptThis("Hello") === "72olle"
encryptThis("good") === "103doo"
encryptThis("hello world") === "104olle 119drlo"
```

### 문제 풀이

```jsx
var encryptThis = function(text) {
  let aText = text.split(' '),
      aResult = [];
  
  for(let text of aText) {
    if (text.length === 1) {
      aResult.push(text.charCodeAt(0));
    } 
    else {
      let aTemp = text.split(''),
          temp = aTemp[1];
      
      aTemp[0] = aTemp[0].charCodeAt(0);
      aTemp[1] = aTemp[text.length - 1];
      aTemp[text.length - 1] = temp;

      aResult.push(aTemp.join(''));
    }
  }

  return aResult.join(' ');
}
```
