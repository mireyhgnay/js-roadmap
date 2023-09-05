# <div align="center">📍 switch문</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - switch](https://ko.javascript.info/switch)

<br>

## 복수의 if 조건문은 switch 문으로 변경할 수 있습니다.

```jsx
let a = 2 + 2;

switch (a) {
  case 3:
    alert("비교하려는 값보다 작습니다.");
    break;
  case 4:
    alert("비교하려는 값과 일치합니다.");
    break;
  case 5:
    alert("비교하려는 값보다 큽니다.");
    break;
  default:
    alert("어떤 값인지 파악이 되지 않습니다.");
}

// result : "비교하려는 값과 일치합니다" (case 4 문이 실행됩니다.)
```

- 변수 a의 값과 case문의 값들을 순서대로 비교하면서 과정이 반복됩니다.
- case문에서 일치하는 값을 찾으면 해당 case문의 코드가 실행됩니다.
- break; 를 만나거나 switch 문이 끝나면 코드의 실행은 멈춥니다.
- 값과 일치하는 case문이 없다면, default문 코드가 실행됩니다. (default문이 있는 경우에만!)

<br>

⇒ case 3은 일치하지 않으니 넘어가고, case 4는 값이 일치하니 실행된다. 그리고 break; 문을 만났으니까 거기서 실행은 멈춘다.

<br>
<br>

## 만약 break 문이 없다면?

case문 안에 break; 가 없다면 조건에 부합하는지 여부를 따지지 않고 이어지는 case문을 모두 실행합니다.

```jsx
let a = 2 + 2;

switch (a) {
  case 3:
    alert("비교하려는 값보다 작습니다.");
  case 4:
    alert("비교하려는 값과 일치합니다.");
  case 5:
    alert("비교하려는 값보다 큽니다.");
  default:
    alert("어떤 값인지 파악이 되지 않습니다.");
}

// result : case 4,5,6, default 모두 실행됨
```

- 일치하는 case문 부터 swtich 문 끝까지 모두 실행되는 것

<br>
<br>

## switch…case 문의 인수엔 어떤 표현식이든 올 수 있습니다.

```jsx
let a = "1";
let b = 0;

switch (+a) {
  case b + 1:
    alert("표현식 +a는 1, 표현식 b+1는 1이므로 이 코드가 실행됩니다.");
    break;

  default:
    alert("이 코드는 실행되지 않습니다.");
}

// result : "표현식 +a는 1, 표현식 b+1는 1이므로 이 코드가 실행됩니다."
```

- +a로 “1” 문자열을 숫자 1로 변환해줍니다.
- case b + 1 은 1 이기 때문에 인수에서 나온 값과 일치하므로 실행되고 마무리됩니다.

<br>
<br>

## switch…case문에서는 자료형이 중요합니다.

```jsx
let arg = prompt("값을 입력해주세요.");

switch (arg) {
  case "0":
  case "1":
    alert("0이나 1을 입력하셨습니다.");
    break;

  case 2:
    alert("이 코드는 절대 실행되지 않습니다!");
    break;
  default:
    alert("알 수 없는 값을 입력하셨습니다.");
}
```

<br>

⭐ prompt 함수에 숫자를 입력하면, 모두 문자열로 변환됩니다!

- 0, 1을 입력하면 ‘0’ ‘1’ 로 들어오기 때문에 첫번째 alert가 잘 실행됩니다.
- 2를 입력하면 ‘2’ 로 들어오기 때문에 2 와는 일치하지 않아 실행되지 않고, default 문으로 넘어가 실행됩니다.
- **`0 ≠ “0”`**
