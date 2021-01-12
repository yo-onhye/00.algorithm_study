# Goldbach's conjecture (Prime numbers)

https://www.codewars.com/kata/56cf0eb69e14db4897000b97

### 문제 설명

Goldbach's conjecture is one of the oldest and best-known unsolved problems in number theory and all of mathematics. It states:

Every even integer greater than 2 can be expressed as the sum of two primes. For example:

`6 = 3 + 38 = 3 + 510 = 3 + 7 = 5 + 512 = 5 + 7`

Some rules for the conjecture:

- pairs should be descending like [3,5] not [5,3]
- all pairs should be in ascending order based on the first element of the pair: `[[5, 13], [7, 11]]` is acceptedbut `[[7, 11],[5, 13]]` is not accepted.

Write the a function that find all identical pairs of prime numbers:

```
def goldbach(even_number)
```

You should return an array of containing pairs of primes, like:

```
[[5, 13], [7, 11]]  # even_number = 18
```

or

```
[[3, 31], [5, 29], [11, 23], [17, 17]] # even_number = 34
```

### 문제 풀이

```jsx
function goldbach(even_number) {
  let aResult= [];

  for(let i = 3; i <= even_number/2; i++) {
    let temp = []; 
    if(isPrime(i) && isPrime(even_number - i)) {
        aResult.push([i, even_number - i]);
    }
  }
	function isPrime(num) {
		for (i = 2; i < num; i++) {
			if (num % i === 0) { return false; }
		}
    return true;
	}
  return aResult;
}
```
