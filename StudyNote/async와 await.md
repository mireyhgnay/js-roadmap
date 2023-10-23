# <div align="center">📍 async 와 await</div>

<br>

### Reference

🔗 https://ko.javascript.info/async-await

[🔗 https://velog.io/@khy226/동기-비동기란-Promise-asyncawait-개념](https://velog.io/@khy226/%EB%8F%99%EA%B8%B0-%EB%B9%84%EB%8F%99%EA%B8%B0%EB%9E%80-Promise-asyncawait-%EA%B0%9C%EB%85%90)

🔗 https://joshua1988.github.io/web-development/javascript/js-async-await/

<br>

자바스크립트의 비동기 처리 패턴 중 가장 최근에 나온 문법으로

기존의 비동기 처리 방식인 콜백함수와 프로미스의 단점을 보완하고 개발자가 읽기 좋은 코드를 작성할 수 있도록 도와준다.

특히 복잡했던 프로미스를 좀 더 편하게 사용할 수 있다.

```jsx
async function f() {
  await 비동기_처리_메서드_명();
}
```

<br>
<br>

## async 함수

function 앞에 위치하고, function 앞에 `async`를 붙이면 해당 함수는 항상 프라미스를 반환한다.

프로미스가 아닌 값을 반환하더라고 resolved promise로 값을 감싸 이행된 프로미스가 반환되도록 한다.

```jsx
async function f() {
  return 1;
}
```

```jsx
async function f() {
  return Promise.resolve(1);
}
```

두개 모두 f().then(alert); 로 실행해도 모두 1 알럿창을 띄운다.

즉, 반드시 async 가 붙은 함수는 반드시 프로미스를 반환한다.

<br>
<br>

## await

await는 async 함수 안에서만 동작한다.

프로미스가 처리될 때까지 기다리는 역할으 한다. 그 결과는 그 이후에 반환된다.

```jsx
async function f() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("완료!"), 1000);
  });

  let result = await promise; // 프라미스가 이행될 때까지 기다림 (*)

  alert(result); // "완료!"
}

f();
```

- 함수를 호출한다.
- 함수 본문이 실행되는 도중에 (\*) 표시한 줄에서 실행이 잠시 중단되었다가 프로미스가 처리되면 실행이 재개된다.
- 1초 뒤에 완료! 가 출력된다.
- `await`는 `promise.then`보다 좀 더 세련되게 프라미스의 `result` 값을 얻을 수 있도록 해주는 문법이다. `promise.then`보다 가독성 좋고 쓰기도 쉽다.

<br>

`await`는 말 그대로 **프라미스가 처리될 때까지 함수 실행을 기다리게** 만든다.

프로미스가 처리되길 기다리는 동안엔 다른 스크립트를 실행하거나 이벤트 처리 등을 할 수 있기 때문에 CPU 리소스가 낭비되지 않습니다.

<br>
<br>

## try…catch

await가 던진 에러는 try…catch 로 잡을 수 있다.

```jsx
async function f() {
  try {
    let response = await fetch("http://유효하지-않은-주소");
    let user = await response.json();
  } catch (err) {
    // fetch와 response.json에서 발행한 에러 모두를 여기서 잡습니다.
    alert(err);
  }
}

f();
```

에러가 발생하면 제어 흐름이 캐치 블록으로 넘어간다.

<br>
<br>

## **`async/await`는 `Promise.all`과도 함께 쓸 수 있습니다.**

여러 개의 프라미스가 모두 처리되길 기다려야 하는 상황이라면 이 프로미스들을 Promise.all 로 감싸고 여기에 await 를 붙여 사용할 수 있습니다.

```jsx
const fetchList = curationPlanList.map(({ planId }) => {
  return new Promise(async (resolve) => {
    const dealNoList = await fetchPlanDealNoList(planId);
    if (dealNoList.length === 0) return resolve([]);
    const result = await fetchPlanDealList(planId, dealNoList);
    resolve(result);
  });
});
const curationList = await Promise.all(fetchList);
```

fetchPlanDealNoList 와 fetchPlanDealList 두가지 모두 처리되길 기다려야하기 때문에 사용!
