# State

**state**는 컴포넌트에서 동적으로 변하는 데이터를 관리하는 데 사용되는 변수이다. 주로 UI의 특정 부분이 **동적으로 변화해야 할 때** 사용되며 state 상태가 변경되면 컴포넌트가 **자동으로 리렌더링**되어 UI를 업데이트한다.

## 코드

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);
  //const [state, setState] = useState(Initial value)

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => setCount(count + 1)}>Click!</button>
    </div>
  );
}
```

count는 실제 값이 들어있는 변수이고, setCount는 count값을 업데이트할 때 사용하는 함수다.

## const로 선언하는 이유

state를 선언할 때 **const**로 선언하는 이유는 변수 자체를 재할당하지 않고 setState 함수를 통해서 변수의 값을 업데이트 하기 때문이다.

```jsx
const [count, setCount] = useState(0);

count = 1; // 절대 금지
```
