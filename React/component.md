# Component

Component는 재사용이 가능한 독립된 UI 코드 조각이다. Component는 하나의 화면 요소를 나타내며, React 애플리케이션을 구성하는 기본 단위로 사용된다.

Component는 입력(props)을 받아서 출력(UI)를 생성하며, 재사용성과 유지보수성을 높이는 데 도움을 준다. 이러한 특성 덕분에 대규모 애플리케이션에서도 호율적으로 개발과 관리를 할 수 있다.

## 코드

React에서 Component는 부모 컴포넌트와 자식 컴포넌트로 나눠 서로 조합하여 사용할 수 있다. 부모 컴포넌트는 자식 컴포넌트를 포함하고, 자식 컴포넌트는 독립적으로 UI를 정의한다.

#### 부모 Component:

```jsx
const Parent = () => {
  return (
    <div>
      <Child />
      <Child />
      <Child />
    </div>
  );
};
```

#### 자식 Component:

```jsx
const Child = () => {
  return <h1>Hello, world!</h1>;
};
```

### 결과

위 코드는 결과적으로 아래와 같은 HTML 구조를 생성한다.

```html
<div>
  <h1>Hello, world!</h1>
  <h1>Hello, world!</h1>
  <h1>Hello, world!</h1>
</div>
```

## 장점

React의 Component는 아래와 같은 장점을 가지고 있다.

- 반복적인 개발이 줄어든다.

- UI 수정이 간편해진다.

- 독립성과 확장성
