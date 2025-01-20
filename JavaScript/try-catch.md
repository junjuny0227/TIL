# try-catch문

`try-catch`문은 예외를 처리하기 위한 구문으로, `try` 블록, `catch` 블록, 그리고 선택적으로 `finally` 블록으로 구성된다. `try` 블록에서는 예외가 발생할 가능성이 있는 코드를 실행하며, 예외가 발생하면 `catch` 블록의 코드가 실행된다. `finally` 블록은 예외 발생 여부와 관계없이 항상 실행되며, 전체 구문 종료 전에 실행되는 코드이다.

## 코드

아래는 `try-catch`문의 기본적인 구조이다.

```js
try {
  // 예외가 발생할 가능성이 있는 코드
} catch (error) {
  // 예외(error)가 발생했을 때 실행할 코드
}
```

## 예제

아래는 `try-catch`문을 활용하여 간단히 작성한 API 통신 코드이다.

```js
async function getData() {
  try {
    const response = await fetch(url);
    const data = await response.json();
    console.log(data); // 데이터를 처리하거나 출력
  } catch (error) {
    console.error(error); // 오류 발생 시 에러 메시지 출력
  } finally {
    console.log("작업 종료"); // 작업 종료 메시지 출력
  }
}
```
