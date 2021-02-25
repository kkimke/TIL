## function

<br>

### 함수

- 여러가지 동작들을 목적대로 묶은 명령
- 각 명령의 시작과 끝을 명확하게 구별할 수 있고, 이에 이름을 붙여 재사용이 가능하다.
- 내장함수 : js에서 미리 만들어 놓은 함수 ex) alert()
- 함수를 선언/정의 -> 함수를 호출/실행

```js
// 두 수를 더하는 함수

function addNumber(a, b) {
  var sum = a + b;
  alert(sum);
}

addNumber(2, 3); // 5
```

<br>

### 함수 실행 순서

- 웹 브라우저에서 js 코드를 해석할 때 '함수 선언 부분'을 가장 먼저 한다.
- 즉 어느 곳에든 함수를 선언해 놓기만 하면 '선언한 위치와 상관없이 함수를 실행'할 수 있다.
- 그래서 보통 한 파일 안에 여러 함수를 선언했을 때, 스크립트 소스의 앞부분이나 뒷부분에 선언 부분을 모아놓고 필요할 때마다 호출하여 사용한다.

```js
addNumber();

function addNumber() {
    ...
}
```

<br>

### 재사용가능한 함수

- 값을 고정하지 않고, 함수 밖에서 값을 제공하여 사용
- 매개변수(parameter) : 외부에서 값을 받아와주는 변수, 다른 변수와 겹치지 않는 변수이름 사용, 여러 개 사용 시 쉼표로 구분
- 인수(argument) : 매개변수에 들어가는 실제 값

```js
function addNumber(num1, num2) {
  // 함수 선언시 parameter
  var sum = num1 + num2;
  return sum; //return (결괏값 sum을 함수 호출위치 result로 넘김)
}

var result = addNumber(2, 3); // 함수 호출시 argument
document.write("두 수를 더한 값: " + result);
```

```js
// 간단 version - sum에 저장하지 않고 바로 return

function addNumber(num1, num2) {
  return num1 + num2;
}

var result = addNumber(2, 3);
document.write("두 수를 더한 값: " + result);
```

<br>

### 매개변수 기본값 지정

```js
function multiple(a, b = 5, c = 10) {
  return a * b + c;
}

multiple(5, 10, 20); // a=5, b=10, c=20
multiple(10, 20); // a=10, b=20, c=10
multiple(30); // a=30, b=5, c=10
```

<br>

### 익명 함수

- 이름이 없는 함수
- 변수에 할당하여 사용하거나, 다른 함수의 매개변수로 사용할 수 있음

```js
// 변수에 할당

let sum = function (a, b) {
  return a + b;
};

document.write("함수 실행 결과: ", sum(10, 20)); // 30
```

### 즉시 실행 함수

- 한 번만 실행하는 함수

```js
(function () {
  let userName = prompt("이름을 입력하세요");
  document.write("안녕하세요? " + userName + "님!");
})();
```

<br>

### 화살표 함수

- ES6 추가
- 익명 함수에서만 사용 가능

(매개변수 없을때)

```js
// 일반

const hi = function () {
  return "안녕하세요?";
};
```

```js
// 화살표
const hi = () => {
  return "안녕하세요?";
};
```

```js
const hi = () => "안녕하세요?";
// {}, return 생략 가능
```

<br>
(매개변수가 1개)

```js
// 일반
const hi = function (user) {
  document.write(user + "님 안녕하세요?");
};
```

```js
// 화살표
const hi = (user) => {
  document.write(user + "님 안녕하세요?");
};
// ()생략 가능
```

<br>
(매개변수가 2개)

```js
// 일반
const sum = function (a, b) {
  return a + b;
};
```

```js
// 화살표
const sum = (a, b) => {
  return a + b;
};
```

```js
const sum = (a, b) => a + b;
//{}, return 생략가능
```
