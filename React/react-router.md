# React-Router

React Router는 React 애플리케이션에서 클라이언트 측 라우팅을 구현하는 데 사용되는 라이브러리이다. 클라이언트 측 라우팅이란 페이지를 새로 고침하지 않고도 애플리케이션 내에서 다양한 경로로 이동할 수 있게 해주는 기능이다.

## 라우팅

React Router를 사용하면 URL 경로에 따라 다른 컴포넌트나 페이지를 렌더링할 수 있다. 전통적인 라우팅은 페이지 전체가 새로고침 되는 방식인 반면, 클라이언트 측 라우팅은 단일 페이지 애플리케이션(SPA)여서 페이지를 다시 로드하지 않고 컴포넌트가 교체되도록 한다.

## 코드

```jsx
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Home from "./pages/Home";
import About from "./pages/About";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />}></Route>
        <Route path="/about" element={<About />}></Route>
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

## Link

React Router에서 페이지 간 이동을 위한 링크를 제공하는 컴포넌트이다. 기존의 HTML의 a태그 대신 사용되며 페이지를 새로 고침하지 않고 애플리케이션 내에서 경로 이동이 가능하다.

```jsx
function Home() {
  return (
    <div>
      <Link to="/about">Go to About</Link>
    </div>
  );
}

export default Home;
```
