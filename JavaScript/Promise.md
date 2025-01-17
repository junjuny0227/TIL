# Promise

`Promise`는 JavaScript에서 비동기 작업을 처리하기 위해 사용되는 객체로, 비동기 작업이 완료된 후 그 결과 값을 전달하거나 작업 중 발생한 오류를 처리할 수 있도록 설계된 개념이다.

## 상태

`Promise`는 다음의 세 가지 상태를 가진다.

- **대기**(Pending): `Promise`의 초기 상태로, 비동기 작업이 아직 완료되지 않은 상태

- **이행**(Fulfilled): 비동기 작업이 성공적으로 완료되어 결과 값을 제공한 상태

- **거부**(Rejected): 비동기 작업이 실패하여 오류를 반환한 상태

이 세 가지 상태를 통해 `Promise` 객체는 비동기 작업의 진행 상황을 추적하고 결과를 처리할 수 있다.

## Promise() 생성자

`Promise` 생성자는 `Promise`를 지원하지 않는 함수를 감싸 비동기 작업을 `Promise`로 처리할 수 있도록 할 때 사용된다.

```js
const promise = new Promise((resolve, reject) => {
  // 비동기 작업 수행
  if (/* 작업 성공 */) {
    resolve("성공");
  } else {
    reject("실패");
  }
});
```

## 주요 메서드

`Promise`는 다음 메서드들을 사용하여 비동기 작업의 결과를 관리한다.

- `then()`: 작업이 성공적으로 완료되었을 때 실행할 콜백 함수를 지정한다.

- `catch()`: 작업이 실패했을 때 실행할 콜백 함수를 지정한다.

- `finally()`: 작업의 성공 여부와 상관없이 항상 실행할 콜백 함수를 지정한다.

## 예제

```js
const promise = new Promise((reslove, reject) => {
  const success = true;

  if (success) {
    resolve("작업 성공"); // fulfilled
  } else {
    reject("작업 실패"); // rejected
  }
});

promise
  .then((result) => {
    console.log(result); // 성공 시 출력
  })
  .catch((error) => {
    console.error(error); // 실패 시 출력
  })
  .finally(() => {
    console.log("작업이 완료되었습니다.");
  });
```
