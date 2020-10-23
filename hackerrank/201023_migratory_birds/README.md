# Migratory Birds

https://www.hackerrank.com/challenges/migratory-birds/problem

### 문제 설명

You have been asked to help study the population of birds migrating across the continent. Each type of bird you are interested in will be identified by an integer value. Each time a particular kind of bird is spotted, its id number will be added to your array of sightings. You would like to be able to find out which type of bird is most common given a list of sightings. Your task is to print the type number of that bird and if two or more types of birds are equally common, choose the type with the smallest ID number.

For example, assume your bird sightings are of types ***arr = [1,1,2,2,3]***. There are two each of types ***1*** and ***2***, and one sighting of type ***3***. Pick the lower of the two types seen twice: type ***1***.

**Function Description**

Complete the *migratoryBirds* function in the editor below. It should return the lowest type number of the most frequently sighted bird.

migratoryBirds has the following parameter(s):

- *arr*: an array of integers representing types of birds sighted

**Input Format**

The first line contains an integer denoting ***n***, the number of birds sighted and reported in the array ***arr***.The second line describes ***arr*** as ***n*** space-separated integers representing the type numbers of each bird sighted.

### 문제 풀이

```jsx
function migratoryBirds(arr) {
    let max = 1;
    let counter = max;
    let type = 0;

    // 배열 내 최솟값부터 탐색을 위해 배열 정렬
    arr.sort(function(a, b) {  return a - b;});

    for (let i = 0; i < arr.length; i++) {
        max = (arr.lastIndexOf(arr[i]) - arr.indexOf(arr[i])) + 1;
        if (max > counter) {
            // 배열 내 가장 많은 타입을 반환
            counter = max;
            type = arr[i];
        }
    }
    return type;
}
```
