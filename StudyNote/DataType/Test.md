```jsx
let name = "Ilya";

alert(`hello ${1}`); // hello 1

alert(`hello ${"name"}`); // hello name

alert(`hello ${name}`); // hello Ilya
```

`${"name"}` 처럼 문자열로 표현식 안에 넣으면 해당 문자열 그대로 반환된다.

맨날 `${name}` 처럼 변수 형식으로만 많이 써서 순간 헷갈렸다🙀
