# Time Conversion

https://www.hackerrank.com/challenges/time-conversion/problem

### 문제 설명

Given a time in *12-*[hour AM/PM format](https://en.wikipedia.org/wiki/12-hour_clock), convert it to military (24-hour) time.

Note: - 12:00:00AM on a 12-hour clock is 00:00:00 on a 24-hour clock.12:00:00PM on a 12-hour clock is 12:00:00 on a 24-hour clock.

**Example**

- _s='12:01:00PM'_

  Return '12:01:00'.

- _s='12:01:00AM'_

  Return '00:01:00'.

**Function Description**

Complete the *timeConversion* function in the editor below. It should return a new string representing the input time in 24 hour format.

timeConversion has the following parameter(s):

- _string s_: a time in  *12*hour format

**Returns**

- _string_: the time in *24*hour format

**Input Format**

A single string  *s* that represents a time in *12*-hour clock format (i.e.: *hh:mm:ssAM* or *hh:mm:ssPM*).

### 문제 풀이

```jsx
function timeConversion(s) {
	let aTemp = s.split(""),
		aTime = aTemp
			.splice(0, aTemp.length - 2)
			.join("")
			.split(":"),
		isPm = false;

	// 입력받은 값이 오후인지 오전인지 판별하여 불린값 저장
	aTemp[aTemp.length - 2] === "P" ? (isPm = true) : (isPm = false);

	// 오전&오후에 따라 오후일 경우에만 12를 더함. 12시일 경우 예외처리
	if (isPm) {
		let time = "00";
		if (aTime[0] < 13) {
			aTime[0] === "12" ? (time = "00") : (time = Number(aTime[0]) + 12);
			aTime.splice(0, 1, time);
		}
	}

	// 정해진 문자열로 반환하기 위해 배열을 : 추가하여 반환
	return aTime.join(":");
}
```
