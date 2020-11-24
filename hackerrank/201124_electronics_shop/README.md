# Electronics Shop

https://www.hackerrank.com/challenges/electronics-shop/problem

### 문제 설명

A person wants to determine the most expensive computer keyboard and USB drive that can be purchased with a give budget. Given price lists for keyboards and USB drives and a budget, find the cost to buy them. If it is not possible to buy both items, return **-1**.

- *int:* the maximum that can be spent, or **-1** if it is not possible to buy both items

**Example**

**b = 60**

**keyboards = [40, 50, 60]**

**drives = [5, 8, 12]**

The person can buy a **40 keyboard + 12 USB drive = 52** , or a **50 keyboard + 8 USB drive = 58**. Choose the latter as the more expensive option and return **58**.

**Function Description**

Complete the *getMoneySpent* function in the editor below.

getMoneySpent has the following parameter(s):

- *int keyboards[n]*: the keyboard prices
- *int drives[m]*: the drive prices
- *int b*: the budget

**Returns**
- int: the maximum that can be spent, or -1 if it is not possible to buy both items

### 문제 풀이

```jsx
function getMoneySpent(keyboards, drives, s){
    let nMax = -1;

    for(let keyboard of keyboards){
        var nTemp = 0;
        for(let drive of drives){
            if(keyboard + drive <= s){
                nTemp = keyboard + drive;
                nMax = nTemp > nMax ? nTemp : nMax;
            }
        }
    }
    return nMax;
}
```
