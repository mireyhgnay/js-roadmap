# <div align="center">📍 네트워크 요청 : fetch</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - fetch](https://ko.javascript.info/fetch)

<br>

자바스크립트를 사용하면 필요할 때 서버에 네트워크 요청을 보내고 새로운 정보를 받아오는 일을 할 수 있습니다.

<br>

기본 문법

```jsx
let promise = fetch(url, [options]);
```

- url : 접근하고자 하는 url
- options : 선택 매개변수, 메소드나 헤더 등을 지정할 수 있음
  - 옵션에 아무것도 넘기지 않으면 url로 부터 콘텐츠가 다운로드 됩니다.

<br>

`fetch()`를 호출하면 브라우저는 네트워크 요청을 보내고 프라미스가 반환됩니다.

HTTP 상태는 응답 프로퍼티를 사용해 확인할 수 있습니다.

- **`status`** – HTTP 상태 코드(예: 200)
- **`ok`** – 불린 값. HTTP 상태 코드가 200과 299 사이일 경우 `true`

<br>

Example)

```jsx
let response = await fetch(url);

if (response.ok) {
  // HTTP 상태 코드가 200~299일 경우
  let json = await response.json();
} else {
  alert("HTTP-Error: " + response.status);
}
```

- `response` 에는 프라미스를 기반으로 하는 다양한 메서드가 있습니다.
  - **`response.text()`** – 응답을 읽고 텍스트를 반환합니다
  - **`response.json()`** – 응답을 JSON 형태로 파싱합니다
  - 기타 등등…
