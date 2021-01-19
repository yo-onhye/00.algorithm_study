# String Breakers

https://www.codewars.com/kata/59d398bb86a6fdf100000031/train/javascript

### 문제 설명

I will give you an integer (N) and a string. Break the string up into as many substrings of N as you can without spaces. If there are leftover characters, include those as well.

```
Example: 

N = 5;

String = "This is an example string";

Return value:
Thisi
sanex
ample
strin
g

Return value as a string: 'Thisi'+'\n'+'sanex'+'\n'+'ample'+'\n'+'strin'+'\n'+'g'
```

### 문제 풀이

```jsx
function stringBreakers(n, string){
    let aTemp = string.replace(/ /g,"").split(''),
        aResult = [],
        word = '';

    for(let i in aTemp) {
        if(i % n === 0) {
            if(word != '') { aResult.push(word); word ='';}
            word += aTemp[i];
        } else {
            word += aTemp[i];
        }     
    }

    if(word != '') {
        aResult.push(word);
    }
    
    return aResult.join('\n');
}
```
