## variable

변수(variable) : 여러 번 값이 바뀔 수 있는 데이터<br>
상수(constant) : 값을 한번 지정하면 바뀌지 않는 데이터

<br>

### 변수 선언

```js
// 한꺼번에 선언하기
let apple, best, chocolate;

// 변수 선언과 값 할당 따로
let apple;
apple = 1000;

// 변수 선언과 값 할당 함께
let apple = 1000;
```

<br>

### let, const

```js
// let

"use strict";

let name = "eun";
console.log(name); // eun
name = "hello";
console.log(name); // hello
```

application마다 쓸 수 있는 메모리가 제한적인데,<br>let이라는 키워드로 name이라는 변수를 정의하면 하나의 박스를 가리키는 포인터가 생긴다.<br>추후에 이곳에 다른 값을 넣어서 저장할 수 있는 것(mutable)

<br>

```js
// const

const daysInWeek = 7;
const maxNumber = 5;
```

constant는 가리키고 있는 포인터가 잠겨있어 변경이 불가능하다.(immutable)<br>보안 문제, 다양한 쓰레드가 동시에 값을 변경, 실수 방지

<br>

### var

let이 ES6에 추가되기 전에 쓰였음<br>

- 문제 : var hoisting-변수 선언 전에 출력이 가능(undefined), block scope이 없음-var은 함수 영역 let const는 블록 영역의 스코프를 가짐, 재선언이 가능

```js
{
  let name = "Eun";
  console.log(name);
  name = "hello";
  console.log(name);
}

console.log(name); // 출력x
```

```js
{
  var name = "Eun";
  console.log(name);
  name = "hello";
  console.log(name);
}

console.log(name); // hello 출력
```

<br>

### 실습) 나이 계산 프로그램

```js
let currentYear = 2021;
let birthYear;
let age;

birthYear = prompt("태어난 연도는 (YYYY)");
age = currentYear - birthYear + 1;
document.write(currentYear + "년 현재<br>");
document.write(birthYear + "년에 태어난 사람의 나이는 " + age + "세입니다.");
```

<br>

### var hoisting

- 호이스팅 : '끌어올리다'
- 변수의 선언 부분을 스코프의 가장 위쪽으로 (할당 부분은 x)

<br>
//선언되지 않은 y를 사용할 시

-var

```js
// 실제 코드

var x = 10;

function displayNumber() {
  console.log("x is " + x);
  console.log("y is " + y);
  var y = 20;
}

displayNumber();
```

```js
// js해석기가 인식하는 코드

var x = 10;

function displayNumber() {
  var y; // var hoisting (problem)
  console.log("x is" + x);
  console.log("y is" + y);
  y = 20;
}
displayNumber();
// x is 10, y is undefined (오류x)
```

<br>

-let

```js
var x = 10;

function displayNumber() {
  console.log("x is" + x);
  console.log("y is" + y);
  let y = 20;
}
displayNumber();
// x is 10, Cannot access 'y' before initialization (오류o)
```

<br>

### scope

- js에서 변수를 선언하고 사용할 때 '변수가 적용되는 범위'를 스코프라고 한다.
- 지역 변수 local variable : 한 함수 안에서만 사용할 수 있는 변수
- 전역 변수 global variable : 스크립트 소스 전체에서 사용할 수 있는 변수

```js
function addNumber() {
  var sum = 10 + 20; // local variable
  return sum;
}
addNumber(); // 30

console.log(sum); // sum is not defined <- sum은 local variable
```

```js
function addNumber() {
  var sum = 10 + 20;
  multi = 10 * 20; // global variable
}
addNumber();
console.log(multi); // 200
```

- 함수 밖에서 선언하거나
- var빼고 함수 안에서 선언하면 => global variable

<br>

### block scope (let)

{block}을 이용해서 코드를 작성하면, 괄호 밖에서는 안의 내용을 볼 수 없음

```js
function calcSum(n) {
  let sum = 0; // 블록변수 sum
  for (let i = 1; i <= n; i++) {
    sum += i;
  }
  console.log(sum);
}
calcSum(10);
// 55 (1~10까지 더한 값)
```

```js
function calcSum(n) {
  sum = 0; // 전역변수 sum
  for (let i = 1; i <= n; i++) {
    sum += i;
  }
}
calcSum(10);
console.log(sum);
// 55
```

```js
// + 사용자에게 값 입력받아 출력하기

function calcSum(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    sum += i;
  }
  document.write("1부터 " + n + "까지 더하면 " + sum);
}

let userNumber = prompt("얼마까지 더할까요?");
if (userNumber != null) calcSum(userNumber);
```

<br>

### 재선언

- var은 재할당과 재선언이 가능
- let은 재할당 가능, 재선언 불가
- (const는 재할당, 재선언 불가)

```js
function calcSum(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    sum += i;
  }
  sum = 100; // 재선언
  console.log(sum);
}
calcSum(10);
//100
```

```js
function calcSum(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    sum += i;
  }
  let sum = 100;
  console.log(sum);
}
calcSum(10);
// 'sum' has already been declared
```

<br>

### js 변수 사용시 주의

- 전역 변수는 최소한으로 : 예상치 못한 곳에서 값이 달라질 수 있음-오류발생
- var 보다는 let을
