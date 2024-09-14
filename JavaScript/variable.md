# Variables

**Variables**는 코드를 조금 간결하고 쉬운 코드 수정을 위해 사용 <br>
JavaScript에서는 **var, let, const** 3가지 방법으로 변수 사용 가능

## var

```javascript
var num1 = 5;
console.log(num1);
```

**var**는 이런 식으로 사용할 수 있고, 특징은 **재선언**과 **업데이트**가 모두 된다.<br>
하지만 언어의 보호를 받지 못한다는 단점이 있어 **권장하지 않는다**.

## const

```javascript
const num2 = 10;
console.log(num2);
```

**const**는 이런 식으로 사용할 수 있고, **가장 많이 사용**되는 변수 중 하나다.<br>
**재선언**과 **업데이트**가 모두 안되고, 특별한 경우가 아니면 **기본형으로 사용**된다.

## let

```javascript
let num3 = 15;
console.log(num3);
```

**let**는 이런 식으로 사용할 수 있고, **const**와 같이 **많이 사용**되는 변수 중 하나다.<br>
**재선언**은 안되지만 **const**와 다르게 **업데이트**가 되서 업데이트가 **필요한 경우에 사용**한다.
