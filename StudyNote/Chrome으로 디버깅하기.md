# <div align="center">📍 Chrome으로 디버깅하기</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - debugging-chrome](https://ko.javascript.info/debugging-chrome)

<br>

## 디버깅(debugging)은 스크립트 내 에러를 검출해 제거하는 일련의 과정을 의미합니다.

<br>

## 중단점(breakpoint) 은 말 그대로 자바스크립트의 실행이 중단되는 코드 내 지점을 의미합니다.

<br>

## debugger 명령어

아래 예시처럼 스크립트 내에 `debugger` 명령어를 적어주면 중단점을 설정한 것과 같은 효과를 봅니다.

debugger 명령어를 사용하면 브라우저를 켜 개발자 도구를 열고 소스 코드 영역을 띄워 중단점을 설정하는 수고를 하지 않아도 됩니다.

```jsx
function hello(name) {
  let phrase = `Hello, ${name}!`;

  debugger; // <-- 여기서 실행이 멈춥니다.

  say(phrase);
}
```
