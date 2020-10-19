# Breaking the Records

https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem

### 문제 설명

Maria plays college basketball and wants to go pro. Each season she maintains a record of her play. She tabulates the number of times she breaks her season record for most points and least points in a game. Points scored in the first game establish her record for the season, and she begins counting from there.

For example, assume her scores for the season are represented in the array scores = [12, 24, 10, 24]. Scores are in the same order as the games played. She would tabulate her results as follows:

```
                                 Count
Game  Score  Minimum  Maximum   Min Max
 0      12     12       12       0   0
 1      24     12       24       0   1
 2      10     10       24       1   1
 3      24     10       24       1   1
 
```

Given the scores for a season, find and print the number of times Maria breaks her records for most and least points scored during the season.

**Function Description**

Complete the *breakingRecords* function in the editor below. It must return an integer array containing the numbers of times she broke her records. Index  is for breaking *most points* records, and index  is for breaking *least points* records.

breakingRecords has the following parameter(s):

- *scores*: an array of integers

**Input Format**

The first line contains an integer , the number of games. The second line contains  space-separated integers describing the respective values of *score0 ,score1,.....scoren - 1 .*

### 문제 풀이

```jsx
function breakingRecords(scores) {
	let min = scores[0],
			max = scores[0],
			minRecord = 0,
			maxRecord = 0;
	
	for (let i of scores) {
			if (max < i) {
					max = i;
					maxRecord++;
			}
			else if (i < min) {
					min = i;
					minRecord++;
			}
	}
	
	return [maxRecord, minRecord];
}
```
