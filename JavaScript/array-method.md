# 배열(Array) 관련 메서드

## 요소 추가/제거

- `push()`: 배열 끝에 요소 추가

  ```js
  const arr = [1, 2, 3];
  arr.push(4); // [1, 2, 3, 4]
  ```

- `pop()`: 배열 끝 요소 제거

  ```js
  const arr = [1, 2, 3];
  arr.pop(); // [1, 2]
  ```

- `unshift()`: 배열 앞의 요소 추가

  ```js
  const arr = [1, 2, 3];
  arr.unshift(0); // [0, 1, 2, 3]
  ```

- `shift()`: 배열 앞의 요소 제거

  ```js
  const arr = [1, 2, 3];
  arr.shift(); // [2, 3]
  ```

## 요소 검색

- `indexOf()`: 특정 값의 첫번째 인덱스 반환

  ```js
  const arr = [1, 2, 3, 2];
  arr.indexOf(2); // 1
  ```

- `includes()`: 특정 값이 배열에 포함되어 있는지 확인

  ```js
  const arr = [1, 2, 3];
  arr.includes(2); // true
  ```

## 변형

- `map()`: 배열의 각 요소를 변형하여 새로운 배열 반환

  ```js
  const arr = [1, 2, 3];
  const double = arr.map((num) => num * 2); // [2, 4, 6]
  ```

- `filter()`: 조건에 맞는 요소만 걸러내어 새로운 배열 반환

  ```js
  const arr = [1, 2, 3, 4];
  const even = arr.filter((num) => num % 2 === 0); // [2, 4]
  ```

- `reduce()`: 배열을 하나의 값으로 축소

  ```js
  const arr = [1, 2, 3, 4];
  const sum = arr.reduce((acc, num) => acc + num, 0); // 10
  ```

## 정렬 및 뒤집기

- `sort()`: 배열 정렬

  ```js
  const arr = [3, 1, 4, 2];
  arr.sort((a, b) => a - b); // [1, 2, 3, 4]
  ```

- `reverse()`: 배열 순서 뒤집기

  ```js
  const arr = [1, 2, 3];
  arr.reverse(); // [3, 2, 1]
  ```

## 일부 가져오기

- `slice()`: 배열의 일부를 새로운 배열로 반환

  ```js
  const arr = [1, 2, 3, 4];
  const subArray = arr.slice(1, 3); // [2, 3]
  ```

- `splice()`: 배열의 특정 부분을 삭제하거나 교체

  ```js
  const arr = [1, 2, 3, 4];
  arr.splice(1, 2); // [1, 4]
  ```

## 기타

- `forEach()`: 배열의 각 요소에 대해 작업 수행 (반환값 X)

  ```js
  const arr = [1, 2, 3];
  arr.forEach((num) => console.log(num)); // 1 2 3
  ```

- `join()`: 배열 요소를 문자열로 결합

  ```js
  const arr = ["a", "b", "c"];
  const result = arr.join("-"); // a-b-c
  ```

- `concat()`: 배열 합치기

  ```js
  const arr1 = [1, 2];
  const arr2 = [3, 4];
  const merged = arr1.concat(arr2); // [1, 2, 3, 4]
  ```

- `find()`: 조건에 맞는 첫 번째 요소 반환

  ```js
  const arr = [1, 2, 3];
  const found = arr.find((num) => num > 1); // 2
  ```

- `findIndex()`: 조건에 맞는 첫 번째 요소의 인덱스 반환

  ```js
  const arr = [1, 2, 3];
  const index = arr.findIndex((num) => num > 1); // 1
  ```

- `flat()`: 중첩 배열을 평탄화

  ```js
  const arr = [1, [2, 3], [4, [5]]];
  const flatArr = arr.flat(2); // [1, 2, 3, 4, 5]
  ```
