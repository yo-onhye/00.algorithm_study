# Stop gninnipS My sdroW!

https://www.codewars.com/kata/5264d2b162488dc400000001/train/javascript

### 문제 설명

Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.

Examples: spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" spinWords( "This is a test") => returns "This is a test" spinWords( "This is another test" )=> returns "This is rehtona test"

### 문제 풀이

```jsx
function spinWords(string){
  let aString = string.split(' '),
      aResult = [];

  for(let s of aString) {
    let aTemp = s.split('');
    if(s.length > 4) { 
        aTemp.reverse();
    }
    aResult.push(aTemp.join(''));
  }

  return aResult.join(' ');
}
```
