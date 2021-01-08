# IQ Test

https://www.codewars.com/kata/552c028c030765286c00007d/train/javascript

### 문제 설명

Bob is preparing to pass IQ test. The most frequent task in this test is `to find out which one of the given numbers differs from the others`. Bob observed that one number usually differs from the others in **evenness**. Help Bob — to check his answers, he needs a program that among the given numbers finds one that is different in evenness, and return a position of this number.

`!` Keep in mind that your task is to help Bob solve a `real IQ test`, which means indexes of the elements start from `1 (not 0)`

**Examples :**

```
iq_test("2 4 7 8 10") => 3 // Third number is odd, while the rest of the numbers are even

iq_test("1 2 1 1") => 2 // Second number is even, while the rest of the numbers are odd
```

### 문제 풀이

```jsx
function iqTest(numbers){
	let aResult = numbers.split(" ");
	let comp = 0;
  
	for (let i of aResult){
		i % 2 === 0 ? comp++ : comp--;
	}

	for (let i in aResult){
		if ((aResult[i] % 2 === 0) != comp > 0){ return Number(i) + 1;}
	}
}
```
