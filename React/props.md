# Props

**Props**는 Properties의 줄임말로, 상위 컴포넌트에서 하위 컴포넌트로 데이터를 전달하기 위한 React의 주요 기능 중 하나이다.

## 특징

Props는 아래와 같은 특징들을 가지고 있다.

- 부모 자식 간 단방향 데이터 흐름을 유지한다.

- 읽기 전용 속성을 가지며, 하위 컴포넌트에서는 Props를 직접 수정할 수 없다.

- 문자열, 숫자, 배열, 객체, 함수 등 다양한 데이터를 전달할 수 있다.

## 코드

#### 부모 컴포넌트:

```jsx
const Parent = () => {
  const names = ["Jeon", "Park"];

  return (
    <div>
      <Child name={names[0]} />
      <Child name={names[1]} />
    </div>
  );
};
```

#### 자식 컴포넌트:

```jsx
// 방법 1: props를 통해 데이터 접근
const Child = (props) => {
  return <h1>Hello, {props.name}!</h1>;
};

// 방법 2: 구조 분해 할당을 통해 데이터 접근
const Child = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};
```

### 결과

위 코드는 결과적으로 아래와 같은 HTML 구조를 생성한다.

```html
<div>
  <h1>Hello, Jeon!</h1>
  <h1>Hello, Park!</h1>
</div>
```
