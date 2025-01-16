# Fetch API

**Fetch API**는 HTTP 통신을 구성하는 **요청**(Request)과 **응답**(Response)을 JavaScript에서 접근하고 조작할 수 있는 인터페이스를 제공하며, Promise 기반으로 작동해 비동기적으로 데이터를 처리할 수 있다. 이를 통해 서버와 데이터를 주고받거나 JSON 데이터를 쉽게 처리할 수 있다.

## 구성

- `fetch()`: 데이터를 가져오기 위한 메서드로, 네트워크를 통해 서버에서 정보를 요청하거나 받아올 때 사용한다. 기본적으로 `Promise`를 반환하며, 성공적으로 완료되면 `Response` 객체를 반환한다.

- `Headers`: 요청과 응답에 포함되는 헤더 정보를 나타낸다. 헤더는 클라이언트와 서버 간의 통신에서 인증, 데이터 방식, 캐시 정책 등 추가적인 메타데이터를 전달할 때 사용된다.

- `Request`: 서버로의 요청을 나타내는 객체로, URL, 메서드(GET, POST 등), 헤더, 본문 데이터를 포함한다.

- `Response`: 서버로부터의 응답을 나타내는 객체로, 상태 코드(예: `200`, `404`), 헤더, 본문 데이터를 포함한다.

## HTTP 메서드 (HTTP Methods)

서버와 클라이언트 간의 데이터 전송 방식 및 의도를 나타낸다.

- `GET`: 데이터 조회하는 데 사용된다. 서버에서 데이터를 가져오는 요청이며, 본문(body)를 포함하지 않는다.

- `POST`: 데이터를 서버로 전송하여 처리를 요청한다. 주로 새로운 데이터를 생성할 때 사용된다.

- `PUT`: 데이터를 완전히 대체(덮어쓰기)한다. 만약 요청한 데이터가 서버에 존재하지 않으면 데이터를 새로 생성한다.

- `PATCH`: 데이터를 부분적으로 수정한다. PUT이 전체 데이터를 대체하는 것과 달리, PATCH는 일부 필드만 변경할 때 사용된다.

- `DELETE`: 데이터를 삭제한다. 서버에 저장된 특정 데이터를 제거할 때 사용된다.

## HTTP 상태 코드

HTTP 응답에서 서버가 클라이언트에게 요청 처리 결과를 전달하는 숫자 코드이다.

| 상태 코드 | 텍스트        | **의미**        | **설명**                                                                       |
| --------- | ------------- | --------------- | ------------------------------------------------------------------------------ |
| **1xx**   | Informational | 정보            | 요청이 수신되었으며, 클라이언트는 요청을 계속 진행해도 된다는 임시 응답        |
| **2xx**   | Success       | 성공            | 클라이언트의 요청이 성공적으로 처리되었음을 나타냄                             |
| **3xx**   | Redirection   | 리다이렉션      | 요청을 완료하려면 추가 작업(다른 URL로 이동 등)이 필요함을 나타냄              |
| **4xx**   | Client Error  | 클라이언트 에러 | 클라이언트의 요청이 잘못되었거나 처리될 수 없음을 나타냄 (예: 잘못된 URL 요청) |
| **5xx**   | Server Error  | 서버 에러       | 서버가 요청을 처리하는 도중 문제를 발생시켰음을 나타냄                         |

## 사용법

가장 기본적인 사용방법은 아래와 같다.

```js
async function 함수이름() {
  const response = await fetch("API 주소"); // 요청 -> 데이터 저장
  const jsonData = await response.json(); // JSON으로 파싱
  console.log(jsonData);
}
```

## 예제

아래 코드는 OpenWeatherMap API를 사용하여 현재 위치의 날씨 정보를 가져오는 코드이다.

```js
async function handleGeoSuccess(position) {
  const lat = position.coords.latitude; // 위도
  const lon = position.coords.longitude; // 경도

  const response = await fetch(
    `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=API_KEY`
  ); // API 키는 절대로 노출되면 안 된다.

  const weatherData = await response.json();

  console.log(weatherData.weather[0].main); // 날씨 출력 (예: Clouds)
}

function handleGeoError() {
  console.error("위치 정보를 가져올 수 없습니다.");
}

navigator.geolocation.getCurrentPosition(handleGeoSuccess, handleGeoError);
```
