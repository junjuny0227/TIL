# 객체(Object)

**객체**(Object)는 여러 속성을 하나의 변수에 저장할 수 있는 데이터 타입으로, `키(key)-값(value)` 구조를 가지며 이를 객체의 속성(Property)이라 한다. 객체는 데이터를 구조화하여 관리하기 편리하며, 각 속성은 고유한 키를 통해 접근할 수 있다.

## 선언

### 중괄호({})를 사용하여 만드는 방법

```js
const obj = {}; // 초기 속성이 없는 객체

// 값 할당
obj.one = 1;
obj.two = 2;
obj.three = 3;

console.log(obj); // {one: 1, two: 2, three: 3}
console.log(obj.one); // 1
```

```js
const obj = {
  one: 1,
  two: 2,
  three: 3,
}; // 초기 속성이 있는 객체

console.log(obj); // {one: 1, two: 2, three: 3}
console.log(obj.two); // 2
```

### Object 생성자 함수를 사용하여 만드는 방법

```js
const obj = new Object(); // 초기 속성 직접 전달 불가

obj.one = 1;
obj.two = 2;
obj.three = 3;

console.log(obj); // {one: 1, two: 2, three: 3}
console.log(obj.three); // 3
```

## 속성 접근

JavaScript에서는 두 가지 방법으로 객체의 속성에 접근할 수 있다.

### 점 표기법(Dot notation)

```js
const obj = {
  one: 1,
  two: 2,
  three: 3,
};

console.log(obj.one); // 1
console.log(obj.two); // 2
```

### 대괄호 표기법 (Bracket notation)

```js
const obj = {
  one: 1,
  two: 2,
  three: 3,
};

console.log(obj["two"]); // 2
console.log(obj.["three"]); // 3
```

대괄호 표기법은 아래와 같이 활용 가능하다.

```js
const obj = {
  cat: "meow",
  dog: "woof",
};

function animal(obj, property) {
  return obj[property]; // property 값으로 속성에 접근
}

const catSound = animal(obj, "cat");

console.log(catSound); // meow
```

## 조작

### 추가

```js
const obj = {
  cat: "meow",
  dog: "woof",
};

obj.pig = "oink";
obj["cow"] = "moo";

console.log(obj.dog); // woof
console.log(obj.cow); // moo
```

### 삭제

```js
const obj = {
  cat: "meow",
  dog: "woof",
};

delete obj.dog;

console.log(obj.dog); // undefined
```

### 수정

```js
const obj = {
  cat: "meow",
  dog: "woof",
};

obj.cat = "mew";

console.log(obj.cat); // mew
```

### 조회

```js
const obj = {
  cat: "meow",
  dog: "woof",
};

console.log("cat" in obj); // true
console.log("cow" in obj); // false
```

```js
const obj = {
  cat: "meow",
  dog: "woof",
};

for (const key in obj) {
  console.log(`key: ${key}, value: ${obj[key]}`);
}
// key: cat, value: meow
// key: dog, value: woof
```

## 메소드 참조

메소드 뒤에 괄호`()`를 붙이지 않으면, 메소드를 실행하지 않고 메소드 자체(함수 객체)를 참조하게 된다.

```js
const obj = {
  cat: "meow",
  dog: "woof",
  animal: function () {
    return `cat: ${this.cat}, dog: ${this.dog}`;
  },
};

obj.animal(); // cat: meow, dog: woof
obj.animal; // ƒ () { return `cat: ${this.cat}, dog: ${this.dog}`; }
```
