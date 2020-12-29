# Chocolate Feast

https://www.hackerrank.com/challenges/chocolate-feast/problem

### 문제 설명

Little Bobby loves chocolate. He frequently goes to his favorite *5 & 10* store, Penny Auntie, to buy them. They are having a promotion at Penny Auntie. If Bobby saves enough wrappers, he can turn them in for a free chocolate.

**Example**

*n = 15*

*c = 3*

*m =2*

He has *15* to spend, bars cost *3*, and he can turn in *2* wrappers to receive another bar. Initially, he buys *5* bars and has *5* wrappers after eating them. He turns in *4* of them, leaving him with *1*, for *2* more bars. After eating those two, he has *3* wrappers, turns in *2* leaving him with *1* wrapper and his new bar. Once he eats that one, he has *2* wrappers and turns them in for another bar. After eating that one, he only has *1* wrapper, and his feast ends. Overall, he has eaten *5 + 2 + 1 + 1 = 9* bars.

**Function Description**

Complete the *chocolateFeast* function in the editor below.

chocolateFeast has the following parameter(s):

- *int n:* Bobby's initial amount of money
- *int c:* the cost of a chocolate bar
- *int m:* the number of wrappers he can turn in for a free bar

**Returns**

- *int:* the number of chocolates Bobby can eat after taking full advantage of the promotion

**Note**: Little Bobby will always turn in his wrappers if he has enough to get a free chocolate.

**Input Format**

The first line contains an integer, *t*, the number of test cases to analyze.Each of the next *t* lines contains three space-separated integers: *n*, *c*, and *m*. They represent money to spend, cost of a chocolate, and the number of wrappers he can turn in for a free chocolate.
### 문제 풀이

```jsx
function chocolateFeast(n, c, m) {
    let nChoco = parseInt(n/c),
        nWrap = nChoco;

    while(nWrap >= m) {
        nChoco += parseInt(nWrap / m);
        nWrap = parseInt(nWrap / m) + (nWrap % m);
    }
    return nChoco;
}
```
