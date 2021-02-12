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

- 문제 - var는 변수 선언 전에 값 할당이 가능, 값 할당 전에 출력도 가능(undefined), block scope이 없음

- var hoisting : 어디에 선언했는지 상관없이, 항상 '가장 위로' 선언을 끌어올려주는 것
- block scope : {block}을 이용해서 코드를 작성하면, 괄호 밖에서는 안의 내용을 볼 수 없음

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
