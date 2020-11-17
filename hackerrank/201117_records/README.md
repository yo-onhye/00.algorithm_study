# Breaking the Records

https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem

### 문제 설명

Maria plays college basketball and wants to go pro. Each season she maintains a record of her play. She tabulates the number of times she breaks her season record for *most points* and *least points* in a game. Points scored in the first game establish her record for the season, and she begins counting from there.

For example, assume her scores for the season are represented in the array ***scores = [12, 24, 10, 24]***. Scores are in the same order as the games played.

Given the scores for a season, find and print the number of times Maria breaks her records for *most* and *least* points scored during the season.

**Function Description**

Complete the *breakingRecords* function in the editor below. It must return an integer array containing the numbers of times she broke her records. Index ***0*** is for breaking *most points* records, and index ***1*** is for breaking *least points* records.

breakingRecords has the following parameter(s):
- *scores*: an array of integers

### 문제 풀이

```jsx
function breakingRecords(scores) {
    let nMin = 0, 
        nMax = 0,
        nHighest = scores[0],
        nLowest = scores[0];

    for(let score of scores) {
        if(nHighest < score) {
            nHighest = score;
            nMax++;
        }
        if(nLowest > score) {
            nLowest = score;
            nMin++;
        }
    }
    return [nMax, nMin];
    // 최댓값과 최솟값을 변수에 담아 배열을 돌며 원소와 비교
    // 비교의 조겁에 부합할 때 각 값들을 변경하고, 카운팅
}
```
