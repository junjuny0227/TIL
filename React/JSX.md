# JSX

**JSX**는 JavaScript XML의 약자로, JavaScript에 XML 문법을 추가한 확장된 문법이다. JSX를 사용하면 하나의 파일에 HTML과 JavaScript를 동시에 작성할 수 있어 개발이 편리하다. 또한, JavaScript에서 HTML을 작성하듯이 코드를 작성할 수 있어 가독성이 높고 이해하기 쉽다.

## 문법

### 1. 최상위 부모 요소는 오직 하나만 있어야 한다.

JSX에서는 `return` 안에서 여러 개의 최상위 요소를 반환할 수 없으며, 하나의 부모 요소만 반환해야 한다. 그렇지 않으면 문법 오류가 발생한다.

#### 에러 케이스:

```jsx
const App = () => {
  return (
    <div>Hello</div>
    <div>World!</div>
  );
};
```

위 코드에서는 두 개의 `<div>` 요소가 최상위에 나란히 존재하므로 에러가 발생한다.

#### 정상 케이스:

```jsx
const App = () => {
  return (
    <div>
      <div>Hello</div>
      <div>World!</div>
    </div>
  );
};
```

위 코드에서는 두 개의 `<div>` 요소가 하나의 부모 요소인 `<div>` 안에 포함되어 있어 정상적으로 작동한다.

### 2. JavaScript 표현식

JSX 내부에서 JavaScript 표현식을 작성하려면 변수를 중괄호(`{}`)로 감싸줘야 한다. 이를 통해 JSX 안에서 JavaScript 코드를 실행할 수 있다.

```jsx
const App = () => {
  const name = "Jeon";

  return (
    <div>
      <div>Hello</div>
      <div>{name}</div>
    </div>
  );
};
```

### 3. 삼항 연산자

JSX에서는 조건부 렌더링을 할 때 삼항 연산자를 사용할 수 있다. 삼항 연산자는 `조건 ? 참일 때 : 거짓일 때` 형식으로 작성되며, 조건이 `true`일 경우 첫 번째 값을, `false`일 경우 두 번째 값을 반환한다.

```jsx
const App = () => {
  const login = true;

  return (
    <div>
      {login ? <div>로그인 되었습니다.</div> : <div>로그인이 필요합니다.</div>}
    </div>
  );
};
```

위 코드에서 `login`이 `true`일 경우 "로그인 되었습니다."라는 문구가 출력되고, `false`일 경우 "로그인이 필요합니다"라는 문구가 출력된다.

### 4. 인라인 스타일

JSX에서 인라인 스타일은 객체 형태로 작성되어야 하며, CSS 속성 이름은 `-` 대신 `camelCase`로 작성해야 한다. 스타일 속성 값은 문자열이나 숫자로 지정할 수 있다.

```jsx
const App = () => {
  const style = {
    backgroundColor: "skyblue", // background-color -> backgroundColor
    color: "black",
    fontSize: "24px", // font-size -> fontSize
    padding: "1.5rem", // padding -> padding
  };

  return <div style={style}>Hello World</div>;
};
```

위 코드에서 `style` 객체는 CSS 속성들이 `camelCase`로 작성되어 있고, `div` 요소의 `style` 속성에 이 객체를 전달하여 인라인 스타일을 적용한다. 이렇게 하면 배경색, 글자 색, 폰트 크기, 패딩 등을 지정할 수 있다.

### 5. class 대신 className

`class`는 JavaScript에서 예약어이기 때문에 JSX에서는 `class` 대신 `className`을 사용해야 한다. 이는 HTML의 `class` 속성과 동일한 역할을 하지만, JavaScript의 예약어와 충돌을 피하기 위해 이름이 변경된 것이다.

```jsx
const App = () => {
  return (
    <div className="container">
      <div>Hello, World!</div>
    </div>
  );
};
```

위 코드에서 `className="container"`는 `div` 요소에 `container`라는 CSS 클래스를 적용하는 방식이다. JSX에서 스타일을 적용할 때는 반드시 `class` 대신 `className`을 사용해야 한다.
