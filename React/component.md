# Component

**component**란 UI를 **독립적**이고 **재사용 가능한** 조각으로 나누어 구성할 때 사용하는 기본 단위이다.

component는 **반복적인 코드나 UI**를 재사용 가능하게 하여 개발 효율성을 높이고 유지보수를 용이하게 하고, 이를 통해 코드의 일관성을 유지하고, 버그를 줄이며, 개발 속도를 향상시킬 수 있다.

## 예시

![](https://velog.velcdn.com/images/junjuny0227/post/e7712493-b84e-4439-bb1b-1df5e5583a42/image.png)

component 사용 예시로는 구글의 관련 검색어 부분이 있는데, 관련 검색어 부분을 보면 빨간색으로 박스를 쳐놓은 부분이 내용만 바뀌고 **동일한 형식으로 반복**되는 것을 볼 수 있다.

이와 같이 component를 사용하여 개발하면, **반복되는 요소**를 일일이 입력할 필요 없이 **이미 만들어둔 component들을 조합**하여 웹사이트를 만들 수 있다.

## 코드

```jsx
// Hello.js (자식 컴포넌트)

import React from "react";

function Hello() {
  return <h1>Hello, World!</h1>;
}

export default Hello;
```

```jsx
// App.js (부모 컴포넌트)

import React from "react";
import Hello from "./Hello";

function App() {
  return (
    <div>
      <Hello />
      <Hello />
      <Hello />
    </div>
  );
}

export default App;
```
