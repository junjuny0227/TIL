# 배열(Array)

**배열**(Array)은 순서가 있는 데이터(원시 값 또는 객체)의 집합으로, 하나의 변수에 여러 값을 저장하는 데 사용된다. 이를 통해 관련 데이터를 효율적으로 관리하고, 각 요소에 인덱스를 통해 접근할 수 있다.

> 배열의 각 항목에는 번호가 붙어 있으며, 이를 인덱스라고 부른다. 인덱스를 사용하면 배열의 특정 항목에 접근할 수 있다. JavaScript에서 배열은 0부터 시작하는 인덱스를 사용하며, 다양한 메서드를 통해 배열을 조작할 수 있다.

## 선언

### 대괄호([])를 사용하여 만드는 방법

```js
const arr = []; // 초기 값이 없는 배열

// 값 할당
arr[0] = "zero";
arr[1] = "one";
arr[2] = "two";

console.log(arr); // ["zero", "one", "two"]
```

```js
const arr = ["zero", "one", "two"]; // 초기 값이 있는 배열

console.log(arr); // ["zero", "one", "two"]
```

```js
const arr = [, , ,]; // 쉼표의 개수만큼 배열의 크기를 지정

console.log(arr); // [undefined, undefined, undefined]
```

### Array 생성자 함수를 사용하여 만드는 방법

```js
const arr = new Array(); // 초기 값이 없는 배열

// 값 할당
arr[0] = "zero";
arr[1] = "one";
arr[2] = "two";

console.log(arr); // ["zero", "one", "two"]
```

```js
const arr = new Array("zero", "one", "two"); // 초기 값이 있는 배열

console.log(arr); // ["zero", "one", "two"]
```

```js
const arr = new Array(3); // 배열의 크기를 지정

console.log(arr); // [undefined, undefined, undefined]
```
