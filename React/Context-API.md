# Context API

**Context API**는 React에 내장된 API로, Props를 사용하지 않고도 컴포넌트 간 데이터를 손쉽게 공유할 수 있게 한다. 컴포넌트마다 일일이 Props를 전달하지 않아도 컴포넌트 트리 전체에 데이터를 전달할 수 있으며, 특히 전역적으로 사용해야 하는 데이터를 관리할 때 유용하다.

## Prop Drilling

Prop Drilling은 최상위 부모 컴포넌트에서 가장 하위의 자식 컴포넌트로 데이터를 전달해야 할 때, 각 단계의 컴포넌트에서 Props를 계속 전달하고 받아야 하는 작업을 반복하는 문제를 말한다.

이 과정에서 Props가 실제로 필요하지 않은 중간 컴포넌트들까지 데이터를 전달받게 되며, 이는 코드의 복잡성을 높이고 가독성을 떨어뜨린다. 이러한 문제는 컴포넌트 계층이 깊어질수록 더욱 심각해진다.

Prop Drilling 문제를 해결하기 위해 Context API나 상태 관리 라이브러리(예: Redux, Zustand, Recoil)를 활용하면 보다 효율적인 데이터 관리를 할 수 있다.

### 예시

```jsx
const GrandParent = () => {
  const user = { name: "Jeon", age: 18 };

  return <Parent user={user} />;
};

const Parent = ({ user }) => {
  return <Child user={user} />;
};

const Child = ({ user }) => {
  return <h1>Hello, {user.name}!</h1>;
};
```

위 코드는 Child 컴포넌트에서만 user 데이터를 필요로 하지만, GrandParent에서부터 Parent를 거쳐야만 데이터를 전달할 수 있다.

## 주로 사용되는 곳

Context API는 주로 다음과 같은 상황에서 사용된다.

- **테마** (라이트 모드, 다크 모드)

- **사용자 정보** (로그인 유무 등등)

- **선호하는 언어** (다국어 지원)

이 외에도 전역적으로 사용해야 하는 데이터가 있을 때 유용하게 활용할 수 있다.

## 사용

Context API 사용 순서

1. `createContext`를 사용하여 `Context`를 생성한다.

2. 생성한 `Context`의 `Provider`를 사용해 데이터를 전달할 컴포넌트를 감싼다.

3. `Provider`의 `value` 속성을 통해 공유할 데이터를 설정한다.

4. `useContext` 훅을 사용해, 데이터가 필요한 컴포넌트에서 데이터를 가져온다.

## 코드

```jsx
import { createContext } from "react";

// 1. Context 생성
export const MyContext = createContext("기본값");

function Parents() {
  const sharedData = "Hello, Context!";

  // 2. Provider로 감싸고 value에 데이터 전달
  return (
    <MyContext.Provider value={sharedData}>
      <Child1 />
    </MyContext.Provider>
  );
}

export default Parents;
```

```jsx
import { useContext } from "react";
import { MyContext } from "./Parents";

function Child10() {
  // 3. useContext를 사용해 데이터 가져오기
  const data = useContext(MyContext);

  // 4. 데이터를 컴포넌트에서 사용
  return <h1>{data}</h1>;
}

export default Child10;
```
