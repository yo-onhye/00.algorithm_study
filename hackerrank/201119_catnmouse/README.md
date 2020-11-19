# Cats and a Mouse

https://www.hackerrank.com/challenges/cats-and-a-mouse/problem

### 문제 설명

Two cats and a mouse are at various positions on a line. You will be given their starting positions. Your task is to determine which cat will reach the mouse first, assuming the mouse does not move and the cats travel at equal speed. If the cats arrive at the same time, the mouse will be allowed to move and it will escape while they fight.

- *int z*: Mouse ***C***'s position

You are given ***q*** queries in the form of ***x***, ***y***, and ***z*** representing the respective positions for cats ***A*** and ***B***, and for mouse ***C***. Complete the function ***catAndMouse*** to return the appropriate answer to each query, which will be printed on a new line.

- If cat ***A*** catches the mouse first, print `Cat A`.
- If cat ***B*** catches the mouse first, print `Cat B`.
- If both cats reach the mouse at the same time, print `Mouse C` as the two cats fight and mouse escapes.

**Example**

***x = 2***

***y = 5***

***z = 4***

The cats are at positions ***2***(Cat A) and ***5***(Cat B), and the mouse is at position ***4***. Cat B, at position ***5*** will arrive first since it is only ***1*** unit away while the other is ***2*** units away. Return 'Cat B'.

**Function Description**

Complete the *catAndMouse* function in the editor below.

catAndMouse has the following parameter(s):

- *int x*: Cat ***A***'s position
- *int y*: Cat ***B***'s position

### 문제 풀이

```jsx
function catAndMouse(x, y, z) {
    let nCatA = Math.abs(z - x),
        nCatB = Math.abs(z - y);

    if (nCatA < nCatB) {
        return "Cat A";
    } else if (nCatA > nCatB) {
        return "Cat B";
    } else {
        return "Mouse C";
    }
    // A고양이와 쥐의 간격과 B고양이와 쥐의 간격을 절대값으로 저장
    // 간격을 비교하여 맞는 리턴 값 반환
}
```
