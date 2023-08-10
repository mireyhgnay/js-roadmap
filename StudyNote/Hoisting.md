# <div align="center">📍 Hoisting</div>

<br>

### Reference

- [MDN - 호이스팅](https://developer.mozilla.org/ko/docs/Glossary/Hoisting)

<br>
<br>

인터프리터가 변수와 함수의 메모리 공간을 선언 전에 미리 할당하는 것을 의미합니다.

**함수, 변수, 클래스 선언을 스코프 처음으로 이동시켜 우선 실행시킵니다.**

<br>

## 3가지 유형

1. 선언 전 변수 값 사용이 가능 - function
2. 선언 전 에러 없이 변수 참조 가능(값은 undefined) - var
3. 선언 전 변수 접근, 사용시 에러 발생 - let, const, class

<br>

## 3번도 호이스팅!

에러가 발생하여 호이스팅이 아닌 것 같지만 그렇지 않습니다.

```jsx
const x = 1;
{
  console.log(x); // ReferenceError
  const x = 2;
}
```

‘const x = 2’가 호이스팅 대상이 아니라면 문제가 없어야 합니다.

상위 스코프에 변수 x가 있기 때문이죠. 하지만 에러가 발생합니다.  
여기서 블록 안에서 상위 스코프의 x가 유효하지 않음을 알 수 있습니다.

그렇다는 건 블록 안에 같은 이름의 변수 선언이 있다고 할 수 있겠죠.

에러는 `TDZ(Temporal dead zone)`로 인해 발생합니다.  
TDZ는 스코프 시작에서 선언 전까지 접근, 사용이 제한되는 구역을 말합니다.

<br>

## 선언만 호이스팅

초기화는 호이스팅 대상이 아닙니다. 선언이 없으면, 호이스팅은 일어나지 않죠.

```jsx
console.log(num); // 호이스팅 X, ReferenceError
num = 5; // 초기화, 호이스팅 대상 아님
```

<br>

아래 예제를 통해 var 변수는 호이스팅으로 값이 undefined로 초기화 됨을 알 수 있습니다.

```jsx
console.log(num); // 호이스팅, undefined 출력
var num; // 선언, 호이스팅 대상
num = 5; // 초기화, 호이스팅 대상 아님
```
