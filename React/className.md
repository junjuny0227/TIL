# className

JSX 문법에서는 아래와 같이 class 대신 className을 사용한다.

```javascript
function App() {
  return (
    <>
      <div className="App">
        <h1>Welcome back!</h1>
      </div>
    </>
  );
}

export default App;
```

그 이유는 class는 javascript의 예약어이기 때문에 사용할 수 없기 때문이다.

```css
.App {
  display: flex;
  background-color: black;
  font-size: 16px;
}
```

css에서 사용 방법은 기존과 똑같다.
