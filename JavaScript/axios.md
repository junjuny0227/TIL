# Axios

AXIOS는 Promise API를 활용하는 HTTP **비동기** 통신 라이브러리다.

> ## 동기식과 비동기식 차이
>
> <img src="./img/Asynchronous.png" >

## 특징

- 운영 환경에 따라 브라우저간 XMLHttpRequest 객체 또는 Node.js의 HTTP API를 사용한다.
- ES6 Promise API를 사용한다.
- HTTP Methods를 사용한다.
- Request의 응답을 자동으로 JSON 형태로 만든다.

## Fetch와 Axios의 차이 (코드 비교)

### Fetch API

- body안에 정보
- url은 ()안에 인자로
- body는 stringify()

```javascript
const url = "요청할 주소";
const options = {
  method: "POST",
  headers: {
    Accept: "application/json",
    "Content-Type": "application/json;charset=UTF-8",
  },
  body: JSON.stringify({
    name: "test",
  }),
};

fetch(url, options)
  .then((response) => response.json()) // JSON 응답으로 변환
  .then((data) => console.log(data)) // JSON 데이터를 출력
  .catch((error) => console.error("Error:", error)); // 오류 처리
```

### Axios

- data안에 정보
- url은 option 객체 안에 값으로

```javascript
const options = {
  url: "요청할 주소",
  method: "POST",
  headers: {
    Accept: "application/json",
    "Content-Type": "application/json;charset=UTF-8",
  },
  data: {
    name: "test",
  },
};

axios(options)
  .then((response) => console.log(response)) // JSON 데이터를 출력
  .catch((error) => console.error(error)); // 오류 처리
```

## 사용법

### GET (데이터 조회)

> GET 방식은 서버에서 어떠한 데이터를 받아서 보여줄 때 사용한다.
>
> - response는 json형태이다.

```javascript
const getLists = async () => {
  axios
    .get("요청할 주소")
    .then((res) => {
      console.log(res.data);
    })
    .catch((err) => {
      console.log(err);
    });
};
```

### POST (데이터 생성)

> POST 메소드의 두 번째 인자는 요청주소로 보낼 데이터 객체이다
>
> - ex) 업로드, 로그인, 글 작성 등

```javascript
const postList = async () => {
  const { data } = await axios
    .post("요청할 주소", "보낼 값(객체)", {
      headers: {
        "Content-type": "application/json",
        Accept: "application/json",
      },
    })
    .then((res) => {
      console.log(res.data);
    })
    .catch((err) => {
      console.log(err);
    });
};
```

### DELETE (데이터 삭제)

> DELETE 메소드는 데이터베이스의 내용을 삭제합니다.<br>.delete()는 두 번째 인자를 전달하지 않습니다.

```javascript
const deleteList = async (listId) => {
  const { data } = await axios.delete(`요청할 주소/${listId}`);
};
```

### PUT & PATCH (데이터 수정)

> PUT은?<br>
> => 보낸 내용으로 리소스를 덮어씁니다.<br>
> PACTH는?<br>
> => 보낸 내용으로 리소스의 일부를 변경합니다.

```javascript
axios.put("요청할 주소", "덮어쓸 값", config);
axios.patch("요청할 주소", "일부만 바꿀 값", config);
```
