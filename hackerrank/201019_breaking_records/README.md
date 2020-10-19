# Grading Students

https://www.hackerrank.com/challenges/grading/problem

### 문제 설명

HackerLand University has the following grading policy:

- Every student receives a **_grade_** in the inclusive range from **0** to **100**.
- Any **_grade_** less than **40** is a failing grade.

Sam is a professor at the university and likes to round each student's **_grade_** according to these rules:

- If the difference between the **_grade_** and the next multiple of **5** is less than **3**, round **_grade_** up to the next multiple of **5**.
- If the value of **_grade_** is less than **38**, no rounding occurs as the result will still be a failing grade.

**Examples**

- **_grade = 84_** round to **_85_** (85 - 84 is less than 3)
- **_grade = 29_** do not round (result is less than 40)
- **_grade = 57_** do not round (60 - 57 is 3 or higher)

Given the initial value of  **_grade_** for each of Sam's  students, write code to automate the rounding process.

**Function Description**

Complete the function *gradingStudents* in the editor below.

gradingStudents has the following parameter(s):

- _int grades[n]_: the grades before rounding

**Returns**

- _int[n]_: the grades after rounding as appropriate

**Input Format**

The first line **contains a single integer, \***n**_, the number of students. Each line _**i**_ of the _**n**_ subsequent lines contains a single integer, _**grade[i]\*\*\*.

### 문제 풀이

```jsx
function gradingStudents(grades) {
	for (let i of grades) {
		if (i < 38 || i % 5 < 3) {
			console.log(i);
		} else {
			let nRound = 5 - (i % 5);
			console.log(i + nRound);
		}
	}
	// run time 에러가 뜸..
}
```
