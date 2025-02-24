# JavaScript의 문제점

JavaScript는 브라우저가 이해할 수 있는 유일한 언어이지만, 몇 가지 큰 문제점들이 있다.

## 동적 타입

JavaScript의 특징이자 문제점 중 하나는 동적 타입 언어라는 점이다. 이는 변수에 타입을 명시적으로 지정하지 않으면 코드가 실행되는 런타임에 변숫값이 할당될 때 해당 값의 타입에 따라 변수의 타입이 결정된다는 의미다.

## 동적 타이핑의 한계

아래 예시를 살펴보자.

```javascript
// a, b의 합을 반환하는 함수
const sumNumber = (a, b) => {
  return a + b;
};

sumNumber(1, 2); // 3
```

눈으로 보나 실행을 시켜보나 아무런 문제가 없는 정상적인 코드이다. 하지만 아래 코드에서는 의아할 만한 점이 생긴다.

javascript
복사
편집

```javascript
// a, b의 합을 반환하는 함수
const sumNumber = (a, b) => {
  return a + b;
};

sumNumber(5); // NaN
sumNumber("a", "b"); // ab
```

첫 번째 예시와 달리, 인자에 숫자 하나만 전달하거나 문자열을 전달했을 때 의도하지 않은 결과가 나온다. 이는 JavaScript의 동적 타이핑 특성 때문이다. 타입을 명시하지 않으면 입력값에 따라 예기치 않은 동작을 할 수 있다.

## 해결 방안

위 문제들을 TypeScript로 해결할 수 있다. TypeScript는 변수나 함수의 타입을 명시적으로 지정할 수 있기 때문에, 타입 오류를 컴파일 단계에서 잡아낼 수 있다.

```typescript
const sumNumber = (a: number, b: number): number => {
  return a + b;
};

sumNumber(1, 2); // 3
sumNumber(5); // 오류 발생
sumNumber("a", "b"); // 오류 발생
```

위 코드에서는 sumNumber 함수가 숫자 타입의 인자만 받도록 지정되었기 때문에, 숫자가 아닌 값을 전달할 경우 컴파일 단계에서 오류가 발생한다. 이렇게 TypeScript를 사용하면 런타임에서 발생할 수 있는 예기치 않은 오류를 미리 방지할 수 있다.
