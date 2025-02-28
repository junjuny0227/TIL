# useState

`useState`는 React의 기본적인 Hook 중 하나로, 함수형 컴포넌트에서 상태를 관리할 수 있도록 해준다.

## 사용법

`useState`를 사용하려면 먼저 React에서 `useState`를 불러온 뒤, 컴포넌트 내에서 배열 비구조화 할당을 이용해 상태 변수(state)와 상태 변경 함수(setState)를 선언한다.

```jsx
import { useState } from "react";

const MyComponent = () => {
  const [value, setValue] = useState(0);

  return <div>{value}</div>;
};
```

### 설명

`useState(초깃값)`을 호출하면 현재 상태 값과 상태를 업데이트하는 함수를 배열로 반환한다.

- 첫 번째 요소(`value`)는 현재 상태 값이다.

- 두 번째 요소(`setValue`)는 상태를 변경하는 함수이다.

- `setValue(새로운 값)`을 호출하면 React가 상태 변경을 감지하고, 해당 상태를 사용하는 컴포넌트를 자동으로 리렌더링한다.

## 예제 코드

```jsx
const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>현재 카운트: {count}</p>
      <button onClick={() => setCount(count + 1)}>+1</button>
    </div>
  );
};
```
