# Axios

`Axios`는 `Promise` 기반의 HTTP 비동기 통신 라이브러리로, 브라우저와 `Node.js` 환경에서 모두 사용할 수 있다. `Axios`는 HTTP 요청을 간편하게 처리할 수 있도록 도와주며, JSON 데이터 자동 변환, 요청 및 응답 인터셉터, 기본 URL 설정 등 다양한 기능을 제공한다.

## 특징

Axios의 주요 특징은 아래와 같다:

- **`Promise` 기반**: 비동기 작업을 간단하고 직관적으로 처리할 수 있다.

- **`JSON` 데이터 자동 변환**: 응답 데이터를 자동으로 `JSON` 형식으로 처리한다.

- **`Interceptors` 지원**: 요청과 응답에 대해 전/후처리 기능을 추가할 수 있다.

- **요청 취소**: 비동기 요청을 취소할 수 있는 기능을 제공하여, 불필요한 네트워크 요청을 중단할 수 있다.

- **타임아웃 설정**: 요청에 시간 제한을 설정하여, 일정 시간 내에 응답이 없으면 자동으로 취소할 수 있다.

## 사용

### 설치

**npm**으로 설치:

```bash
npm install axios
```

**yarn**으로 설치:

```bash
yarn add axios
```

### 코드

```js
import axios from "axios";

const getData = async () => {
  try {
    const response = await axios.get(url); // GET 요청으로 데이터 가져오기
    console.log(response.data); // 응답 데이터 출력
  } catch (error) {
    console.error(error); // 에러 메시지 출력
  }
};

getData();
```

```js
import axios from "axios";

const postData = async (data) => {
  try {
    const response = await axios.post(url, data); // POST 요청으로 데이터 전송
    console.log(response.data); // 응답 데이터 출력
  } catch (error) {
    console.error(error); // 에러 메시지 출력
  }
};

postData({ name: "Jeon", age: 18 });
```

## Instance

`Instance`는 API 요청 시 공통으로 필요한 설정(config)을 한 곳에 모아 재사용하는 방식이라고 이해하면 된다. `Instance`는 `axios.create`를 사용해 생성하며, 생성 시 매개변수로 전달하는 객체 안에 기본 요청 설정을 정의한다.

### 코드

```js
import axios from "axios";

const instance = axios.create({
  baseURL: "https://api.example.com", // 기본 URL
  timeout: 5000, // 요청 제한 시간 (ms 단위)
  headers: {
    "Content-Type": "application/json", // 요청 헤더 기본값
    Authorization: "Bearer your-token-here", // 인증 토큰 (필요 시)
  },
});

const fetchData = async () => {
  try {
    const response = await instance.get("/data");
    console.log(response.data); // 응답 데이터 출력
  } catch (error) {
    console.error(error); // 에러 메시지 출력
  }
};

fetchUsers();
```

## Interceptor

`Instance`를 사용하면 `Interceptor` 기능을 활용할 수 있다. `Interceptor`는 요청이나 응답을 처리하기 전에 가로채서 로직을 실행할 수 있는 기능이다. 이를 통해 공통적인 작업을 쉽게 처리하거나 에러를 중앙에서 관리할 수 있다.

### 요청(request)을 가로채서 처리하는 상황

- 인증 토큰이 포함되지 않은 경우 요청을 취소하거나, 토큰을 추가한 후 요청을 진행한다.

- 필수 데이터 누락 시 오류를 발생시키거나 요청을 중단한다.

#### 예제 코드

```js
instance.interceptor.request.use(
  (config) => {
    // 요청 전 로직
    const token = localstorage.getItem("authToken");
    if (token) {
      config.headers.Authorization = `Bearer ${token}`;
    } else {
      console.warn("인증 토큰이 없습니다.");
    }
    return config;
  },
  (error) => {
    // 요청 중 에러 발생시
    return Promise.reject(error);
  }
);
```

### 응답(response)을 가로채서 처리하는 상황

- 상태 코드가 200번대가 아닐 경우 실패 처리한다.

- 상태 코드가 401(권한 없음)일 경우, 토큰을 새로 발급받아 재요청을 시도한다.

#### 예제 코드

```js
instance.interceptor.response.use(
  (response) => {
    return response;
  },
  async (error) => {
    // 에러 응답 처리
    if (error.response.status === 401) {
      console.log("권한 없음. 토큰 갱신 중");
      // refresh token 로직
      const newToken = await refreshAuthToken();
      if (newToken) {
        error.config.headers.Authorization = `Bearer ${newToken}`;
        return instance.request(error.config); // 재요청
      }
    }
    return Promise.reject(error); // 그 외 에러
  }
);
```
