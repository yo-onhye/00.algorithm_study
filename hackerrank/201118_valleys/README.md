# Counting Valleys

https://www.hackerrank.com/challenges/counting-valleys/problem

### 문제 설명

- *string path*: a string describing the path

An avid hiker keeps meticulous records of their hikes. During the last hike that took exactly ***steps*** steps, for every step it was noted if it was an *uphill*, ***U***, or a *downhill*, ***D*** step. Hikes always start and end at sea level, and each step up or down represents a ***1*** unit change in altitude. We define the following terms:

- A *mountain* is a sequence of consecutive steps *above* sea level, starting with a step *up* from sea level and ending with a step *down* to sea level.
- A *valley* is a sequence of consecutive steps *below* sea level, starting with a step *down* from sea level and ending with a step *up* to sea level.

Given the sequence of *up* and *down* steps during a hike, find and print the number of *valleys* walked through.

**Example**

***steps = 8 path = [DDUUUUDD]***

The hiker first enters a valley ***2*** units deep. Then they climb out and up onto a mountain ***2*** units high. Finally, the hiker returns to sea level and ends the hike.

**Function Description**

Complete the *countingValleys* function in the editor below.

countingValleys has the following parameter(s):

- *int steps*: the number of steps on the hike

### 문제 풀이

```jsx
function countingValleys(steps, path) {
	let aPath = path.split(''),
        nVally = 0,
        nHeight = 0;

    for(let i of aPath) {
        if(i == 'U') {
            nHeight++;
        } else {
            if(nHeight == 0) {
                nVally++;	
            }
            nHeight--;
        }
    }
    return nVally;
}
```
