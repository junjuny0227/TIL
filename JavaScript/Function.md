# Function

**Function**이란 하나의 특별한 작업을 수행하도록 설계된 독립적인 블록을 의미한다.<br>
**Function**은 어떤 코드를 캡슐화해서 실행을 여러 번 할 수 있게 한다.

```javascript
function 함수명() {
  //code
}
```

**Function**은 이런 형태를 가지고 있다.

```javascript
function printHello() {
  console.log("Hello");
}
```

```javascript
function plus(num1, num2) {
  console.log(num1 + num2);
}

plus(1, 2);
```

**Function**은 이런 식으로 사용할 수 있다.</br>

```javascript
const player = {
  name: "junjun",
  printHello: function (otherName) {
    console.log("Hello " + otherName + " nice to meet you");
  },
};

console.log(player.name);
player.printHello("yeonyeon");
```

**Function**은 **Object**와 함께 사용할 수 있다.
