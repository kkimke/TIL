## condition

<br>

### if, if-else

```js
var number = prompt("숫자 입력");

if (number % 5 === 0) alert("5의 배수");
else alert("5의 배수가 아님");
```

```js
// if-else문 중첩 (prompt창 '취소'버튼 누를 경우)
var number = prompt("숫자 입력");

if (number !== null) {
  if (number % 3 === 0) alert("5의 배수");
  else alert("5의 배수가 아님");
} else alert("입력이 취소됨");
```

<br>

### 실습) 자리 배치도 만들기 - 몇 줄이 필요하나?

```js
var memNum = prompt("입장객은 몇 명인가요?");
var colNum = prompt("한 줄에 몇 명씩 앉나요?");

if (memNum % colNum === 0) rowNum = parseInt(mumNum / colNum);
else rowNum = parseInt(memNum / colNum) + 1;

document.write("모두 " + rowNum + "개의 줄이 필요합니다.");
```

이때 parseInt()함수는 prompt()로 입력받은 값을 정수로 변환<br>
(예상치 못하게 데이터 유형이 자동으로 변환되는 것에 대비)

<br>

### 조건 연산자 활용

(조건) ? true일때 실행할 명령 : false일때 실행할 명령

```js
var number = prompt("숫자 입력");

if (number !== null)
  number % 5 === 0 ? alert("5의 배수") : alert("5의 배수가 아님");
else alert("입력이 취소됨");
```

<br>

### 논리 연산자 활용

```js
// or

var number1 = prompt("50미만의 숫자 입력하기");
var number2 = prompt("50미만의 숫자 입력하기");

if (number1 < 10 || number2 < 10)
  alert("숫자 2개 중 최소한 하나는 10 미만입니다.");
else alert("숫자 2개 중 10 미만인 수가 없습니다.");
```

```js
// and

var number1 = prompt("50미만의 숫자 입력하기");
var number2 = prompt("50미만의 숫자 입력하기");

if (number1 < 50 && number2 < 50) alert("숫자 2개 모두 50 미만입니다.");
else alert("조건에 맞지 않는 수가 있습니다.");
```

빠른 판단을 위해 or 연산자에서는 true가 될 확률이 높은 조건식을 첫 번째로,<br>and 연산자에서는 false가 될 확률이 높은 조건식을 첫 번째로 사용하는 게 좋다.

<br>

### switch

처리할 명령이 많을 때 유용<br>case, break, default 사용

```js
var course = prompt("관심 강의를 선택하세요. 1-주식 2-개발 3-포토샵");

switch (course) {
  case "1":
    document.write("주식 강의는 40,000원");
    break;
  case "2":
    document.write("개발 강의는 30,000원");
    break;
  case "3":
    document.write("포토샵 강의는 20,000원");
    break;
  default:
    alert("잘못 입력했습니다.");
}
```
