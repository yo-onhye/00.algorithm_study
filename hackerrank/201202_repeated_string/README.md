# Angry Professor

https://www.hackerrank.com/challenges/angry-professor/problem

### 문제 설명

A Discrete Mathematics professor has a class of students. Frustrated with their lack of discipline, the professor decides to cancel class if fewer than some number of students are present when class starts. Arrival times go from on time (**arrivalTime ≤ 0**) to arrived late (**arrivalTime > 0**).

Given the arrival time of each student and a threshhold number of attendees, determine if the class is cancelled.

**Example**

**n = 5**

**k = 3**

**a = [-2, -1, 0, 1, 2]**

The first **3** students arrived on. The last **2** were late. The threshold is **3** students, so class will go on. Return `YES`.

**Note:** Non-positive arrival times (**a[i] ≤ 0**) indicate the student arrived early or on time; positive arrival times (**a[i] > 0**) indicate the student arrived **a[i]** minutes late.

**Function Description**

Complete the *angryProfessor* function in the editor below. It must return `YES` if class is cancelled, or `NO` otherwise.

angryProfessor has the following parameter(s):

- *int k*: the threshold number of students
- *int a[n]*: the arrival times of the **n** students

### 문제 풀이

```jsx
function angryProfessor(k, a) {
	let aTemp = a.sort(function(a, b) {  return a - b;}),
			nCnt = 0;

	for(let i of aTemp){
		if(i <= 0) {
			nCnt++;
		}
	}
	return nCnt>=k ? "NO" : "YES"; 
}
```
