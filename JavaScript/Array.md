# Array

**Array**는 많은 변수를 한 번에 선언하기 위해 사용된다.<br>
**Array**의 리터럴 방식은 **[ ] 대괄호**를 사용한다.

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const daysOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"];

console.log(numbers);
console.log(daysOfWeek);
```

기본적으로 **Array**는 이런식으로 사용할 수 있다.

```javascript
const daysOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"];
console.log(daysOfWeek[4]); //컴퓨터는 숫자를 0부터 숫자를 센다 (출력 : "sat")
```

출력할 때 **Array**의 이름 옆에 **[ ]** 를 쓰고 안에 **번호**를 쓰면 **원하는 값만** 출력할 수 있다.

## .push

```javascript
const daysOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"];
console.log(daysOfWeek);

daysOfWeek.push("sun");
console.log(daysOfWeek);
```

**.push**를 사용하면 배열 안에 **값을 추가**할 수 있다.
