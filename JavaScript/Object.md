# Object

**Object**는 배열과 비슷하게 사용할 수 있지만 **하나하나에 의미를 부여해야 할 때** 유용하게 사용한다.<br>
**Object**의 리터럴 방식은 **{ } 중괄호**를 사용한다.

```javascript
const player = {
  name: "junjun",
  points: 100,
  online: true,
};
console.log(player);
```

**Object**의 값 바꾸는 방법

```javascript
player.points = 150; //Object가 const이지만, 구성요소를 바꾸는 것은 상관 X
console.log(player);
```

**Object**에 값 추가하는 방법

```javascript
player.studying = true;
```
