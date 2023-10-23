# <div align="center">📍 async와 await</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - async-await](https://ko.javascript.info/async-await)

[🔗 https://velog.io/@khy226/동기-비동기란-Promise-asyncawait-개념](https://velog.io/@khy226/%EB%8F%99%EA%B8%B0-%EB%B9%84%EB%8F%99%EA%B8%B0%EB%9E%80-Promise-asyncawait-%EA%B0%9C%EB%85%90)

🔗 https://joshua1988.github.io/web-development/javascript/promise-for-beginners/

<br>

동기는 직렬적으로 작동하는 방식이고, 비동기는 병렬적으로 작동하는 방식입니다.

즉, 비동기란 특정 코드가 끝날 때까지 코드의 실행을 멈추지 않고 다음 코드를 먼저 실행하는 것을 의미합니다.

<br>

![동기 비동기](https://github.com/mireyhgnay/js-roadmap/assets/111990266/f6a2534d-74ca-467c-a760-353480741cd3)

- 왼쪽 그림이 비동기로 작동하는 방식 / 오른쪽이 동기적으로 작동하는 방식이다.
- 비동기는 여러 태스크가 동시에 병렬적으로 실행된다.
- 동기는 한 태스크가 끝날때까지 기다렸다가 다음 태스크가 실행된다. 그래서 시간이 오래 걸린다.

<br>
<br>

### 비동기

요청을 보낸 후 응답의 수락 여부와는 상관없이 다음 태스크가 동작하는 방식이다.

이때, 비동기 요청시 응답후 처리할 콜백함수를 함께 알려준다.

해당 태스크가 완료되었을 때, 콜백함수가 호출된다.

<br>

하지만 너무 많은 비동기 처리로 콜백함수가 중첩되어 복잡도가 높아지는 콜백 헬이 발생할 수 있는 단점이 있다.

<br>
<br>

### Promise

자바스크립트는 비동기 처리를 위한 하나의 패턴으로 콜백 함수를 사용한다.

하지만 콜백 헬로 인해 가독성이 나빠질 수 있다는 한계가 있다.

<br>

ES6에서는 비동기 처리를 위한 또 다른 패턴으로 프로미스를 도입했다!

<br>

프로미스는 Promise 생성자 함수를 통해 인스턴스화 한다.

프로미스 생성자 함수는 비동기 작업을 수행할 콜백함수를 인자로 전달 받는데 이 콜백 함수는 resolve 와 reject 함수를 인자로 전달 받는다.

```jsx
// Promise 객체의 생성
const promise = new Promise((resolve, reject) => {
  // 비동기 작업을 수행한다.

  if (/* 비동기 작업 수행 성공 */) {
    resolve('result');
  }
  else { /* 비동기 작업 수행 실패 */
    reject('failure reason');
  }
});
```

<br>

후속 처리 메소드에는 대표적으로 then(프로미스 반환)과 catch(예외) 가 있다.

<br>
<br>

### Promise 체이닝

프로미스는 후속 처리 메소드인 then, catch 로 메소드 체이닝하여 여러개의 프로미스를 연결하여 사용할 수 있다. 이러써 콜백 헬을 해결한다.

```jsx
// 포스트 id가 1인 포스트를 검색하고 프로미스를 반환한다.
promiseAjax("GET", `${url}/1`)
  // 포스트 id가 1인 포스트를 작성한 사용자의 아이디로 작성된 모든 포스트를 검색하고 프로미스를 반환한다.
  .then((res) => promiseAjax("GET", `${url}?userId=${JSON.parse(res).userId}`))
  .then(JSON.parse)
  .then(render)
  .catch(console.error);
```
