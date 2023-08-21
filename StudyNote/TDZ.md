# <div align="center">📍 TDZ(Temporal Dead Zone)</div>

<br>

## Reference

- [TDZ 이란?](https://noogoonaa.tistory.com/78)

<br>
<br>

let, const는 호이스팅 대상이지만 TDZ로 인해 선언 전까지 접근, 사용이 불가능하다고 했습니다.

let, const 말고 TDZ를 가지는 것들이 더 있습니다.

<br>

## class

선언 전에 클래스를 사용할 수 없습니다.

```jsx
const me = new Person("Hailey"); // ReferenceError

class Person {
  constructor(name) {
    this.name = name;
  }
}
```

<br>

다음과 같이 선언 후에 사용합니다.

```jsx
class Person {
  constructor(name) {
    this.name = name;
  }
}

const me = new Person("Hailey");
console.log(me.name); // Hailey
```

<br>

## class constructor 내부의 super

Person 클래스를 상속받은 Race 클래스로 호빗을 만들어 보겠습니다.

```jsx
class Race extends Person {
  constructor(category, name) {
    this.category = category;
    super(name);
  }
}

const frodo = new Race("Hobbit", "Frodo");
```

<br>

코드를 실행하면 에러가 발생합니다.

```bash
VM200:9 Uncaught ReferenceError: Must call super constructor in derived class before accessing 'this' or returning from derived constructor
```

이를 해결하려면 super를 먼저 호출하도록 순서를 바꾸면 됩니다.

<br>

```jsx
class Race extends Person {
  constructor(category, name) {
    super(name);
    this.category = category;
  }
}
```

super를 호출 후 this 선언이 있을 것이라 짐작할 수 있습니다.

super 호출 전까지 this는 TDZ에 있다고 할 수 있겠죠.

super는 상위 클래스의 생성자(constructor)를 호출합니다.

<br>

## 기본 함수의 매개변수

매개변수의 스코프는 전역과 함수의 중간에 위치한다고 합니다.

다음 코드를 실행하면 에러가 발생합니다.

```jsx
const n = 2;

function double(n = n) {
  // ReferenceError
  return n * 2;
}

double();
```

<br>

'n = n'에서 오른쪽 n은 전역 스코프의 상수 n이 아닙니다.

중간 스코프의 n이죠. 선언 전 사용으로 에러가 발생한 것입니다.

상수 n을 기본 값으로 넣으려면 다음과 같이 하면 되겠죠.

```jsx
const init = 2;

function double(n = init) {
  return n * 2;
}

double();
```

<br>

## 번외: TDZ에 해당하는 않는 것들

var, function은 이미 다뤘고, import가 있습니다. 다음과 같이 쓸 수 있습니다.

```jsx
test(); // 문제없어!
import { test } from "./testModule";
```

그래도 import는 처음으로 올리는게 좋겠죠. 🙂
