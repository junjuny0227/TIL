# Fetch

Fetch API는 HTTP 파이프라인을 구성하는 요청과 응답 등의 요소를 JavaScript에서 접근하고 조작할 수 있는 인터페이스를 제공한다.

또한 Fetch API가 제공하는 fetch() 메서드로 네트워크의 리소스를 쉽게 비동기적으로 취득할 수도 있다.

> 기본적인 형태
>
> ````````javascript
> fetch(
>    "http://example.com/movies.json"
>  )
>    .then((response) => {
>      return response.json(); // JSON 응답을 파싱
>    })
>    .then((data) => {
>      console.log(data); // 파싱된 데이터 사용
>    });```````;
> ````````
>
> 또는
>
> ```javascript
> async function logJSONData() {
>   const response = await fetch("http://example.com/movies.json");
>   const jsonData = await response.json();
>   console.log(jsonData);
> }
> ```
