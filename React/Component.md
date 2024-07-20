# Component

React의 컴포넌트는 UI를 독립적이고 재사용 가능한 조각으로 나누어 구성하는 기본 단위이다.

컴포넌트는 크게 함수형 컴포넌트와 클래스형 컴포넌트로 나뉜다.

## 함수형 컴포넌트

함수형 컴포넌트는 JavaScript 함수로 정의된다.

```javascript
import React from "react";

function Greeting(props) {
  return (
    <h1>Hello, {props.name}</h1>
    <span>Welcome!!</span>
  );
}

export default Greeting;
```

## 클래스형 컴포넌트

클래스형 컴포넌트는 ES6 클래스 문법을 사용하여 정의한다.

```javascript
import React, { Component } from 'react';

class Greeting extends Component {
  render() {
    return (
      <h1>Hello, {props.name}</h1>
      <span>Welcome!!</span>
    );
  }
}

export default Greeting;
```

## 결론

React 컴포넌트는 애플리케이션을 모듈화하고 재사용 가능한 단위로 나누는 강력한 도구이다. 함수형 컴포넌트와 클래스형 컴포넌트를 적절히 사용하면 복잡한 UI를 효율적으로 구성할 수 있다.
