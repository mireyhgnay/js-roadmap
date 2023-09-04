# <div align="center">📍 while과 for 반복문</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - while-for](https://ko.javascript.info/while-for)

<br>

반복문을 사용하면 동일한 코드를 여러 번 반복할 수 있습니다.

## 'while' 반복문

```jsx
while (condition) {
  // 반복문 본문
}
```

<br>

condition(조건)이 truthy이면 반복문 본문의 코드가 실행됩니다.

```jsx
let i = 0;
while (i < 3) {
  console.log(i);
  i++;
}

// 0, 1, 2 출력
```

<br>

반복문 조건에는 비교 뿐만 아니라 표현식, 변수가 올 수 있습니다.

조건은 while 에 의해 평가되고, 평가 후엔 불린값으로 변경됩니다.

```jsx
let i = 3;
while (i) {
  console.log(i);
  i--;
}
```

- i가 감소되면서 0이되면 false 가 되므로 반복문이 멈춥니다.

<br>

**본문이 한 줄이면 중괄호를 쓰지 않아도 됩니다.**

```jsx
let i = 3;
while (i) console.log(i--);
```

<br>
<br>

## 'for' 반복문

```jsx
for (begin; condition; step) {
  // ... 반복문 본문(body) ...
}

for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2 출력
}
```

- begin : 반복문에 진입할 떄 단 한 번 실행됩니다.
- condition : 반복마다 해당 조건이 확인됩니다. false면 반복문을 멈춥니다.
- body : condition이 truthy일 동안 계속 실행됩니다.
- step : 각 반복의 body가 실행된 이후에 실행됩니다.

<br>

## 인라인 변수 선언

**👉 인라인 변수 선언**

```jsx
for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
console.log(i); // Error : i is not defined
```

- for문 안에서 let i = 0; 을 선언했기 때문에 for문 안에서만 유효한 것

<br>

**👉 정의되어 있는 변수 선언**

```jsx
let i = 0;

// 기존에 정의된 변수 사용
for (i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
console.log(i); // 3
```

- 반복문 밖에서 선언한 변수이므로 사용할 수 있음

<br>
<br>

## 반복문 빠져나오기 "break"

대개는 반복문 조건이 falsy가 되면 반복문이 종료됩니다.

그런데 `break` 를 사용하면 언제든 원하는 때에 반복문을 빠져나올 수 있습니다.

```jsx
let sum = 0;

while (true) {
  let value = +prompt("숫자를 입력하세요", "");

  if (!value) break; // 아무런 입력 값이 없으면 반복문을 종료합니다.

  sum += value;
}

alert("합계: " + sum);
```

- 사용자에게 일련의 숫자를 입력하도록 안내하고,

- 사용자가 아무런 값도 입력하지 않거나 Cancel 버튼을 눌렀을 때 반복문을 종료합니다.

<br>
<br>

## 다음 반복으로 넘어가기 "continue"

continue 는 전체 반복문을 멈추지 않습니다.

현재 반복을 종료시키고 다음 반복으로 넘어가고 싶을 때 사용할 수 있습니다.

<br>

```jsx
for (let i = 0; i < 10; i++) {
  // 조건이 참이라면 남아있는 본문은 실행되지 않습니다.
  if (i % 2 == 0) continue;

  alert(i); // 1, 3, 5, 7, 9가 차례대로 출력됨
}
```

- i가 짝수이면 continue 가 본문 실행을 중단시키고 다음 이터레이션이 실행되게 합니다.

- 따라서 alert함수는 인수가 홀수일 때만 호출되는 것!

> 굳이 꼬아서 생각할 필요강 없으니.. 특별한 경우가 아니면 continue 는 잘 안쓸듯..........?
