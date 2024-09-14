# Props

**props**는 component 간에 **데이터를 전달**하기 위해 사용되는 중요한 개념이다.

props는 **properties**의 줄임말로, 부모 컴포넌트가 자식 컴포넌트에게 값을 전달할 때 사용되며, props는 자식 컴포넌트가 **읽기만 할 수 있는 불변 객체**로, 자식 컴포넌트는 전달받은 props를 **직접 수정할 수 없다.**

## 예시

![](https://velog.velcdn.com/images/junjuny0227/post/874a1ec0-7bf6-4c6b-ae27-ec393de65163/image.png)

위 사진에서 파란줄이 쳐져있는 부분이 props의 예시인데, props는 컴포넌트에 데이터를 전달하는 역할을 한다. (예: "리액트 기초" ↔ "리액트 네이티브")

> 이해를 돕기 위한 이미지
> ![](https://velog.velcdn.com/images/junjuny0227/post/774da0b7-1d8a-4e3a-9fab-83825cf9227c/image.png)

## 코드

```jsx
// App.js (부모)

import React from "react";
import HelloWorld from "./HelloName";

function App() {
  const names = ["John", "Jane", "Doe"];

  return (
    <div>
      <HelloName name={names} />
    </div>
  );
}

export default App;
```

```jsx
// HelloName.js (자식)

import React from "react";

function HelloName(props) {
  return <h1>Hello, {props.name[1]}! // Hello, Jane!</h1>;
}

export default HelloName;
```
