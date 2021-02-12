## loop

- 초깃값과 반복 크기가 일정하다면 for문
- 그렇지 않고 조건만 주어진다면 while문 활용

<br>

### for문

```
for (초깃값; 조건; 증가식) {
    실행할 명령
}
```

```js
// 1부터 5까지 더하기

var i;
var sum = 0;

for (i = 1; i < 6; i++) {
  sum += i;
}
document.write("1부터 5까지 더하면 " + sum);
```

### 중첩된 for문

```js
// 구구단 만들기

var i, j;

for (i = 1; i <= 9; i++) {
  document.write(i + "단");
  for (j = 1; j <= 9; j++) {
    document.write(i + "X" + j + "=" + i * j + "<br>");
  }
}
```

<br>

### while, do-while문

while문은 조건이 true인 동안 명령을 반복

```
while(조건) {
    실행할 명령
}
```

```js
// 팩토리얼 계산

var n = prompt("숫자를 입력하세요.");
var result = "";

if (n !== null) {
  var nFact = 1; // 결과값
  var i = 1; // 카운터

  while (i <= n) {
    nFact *= i;
    i++;
  }
  result = n + "! = " + nFact;
} else result = "값을 입력하지 않았습니다.";

document.write(result);
```

<br>

do-while문은 일단 명령을 한 번 실행한 후, while문에서 조건을 체크<br>즉 조건이 false라 하더라도 최소한 한 번 실행

```
do {
    실행할 명령
} while(조건)
```

<br>

### break 사용

특정 조건에서 반복문 멈추기

```js
// 구구단 3단까지만 표시

var i, j;

for (i = 1; i <= 9; i++) {
  document.write("<h1>" + i + "단</h1>");
  for (j = 1; j <= 9; j++) {
    document.write(i + "X" + j + "=" + i * j + "<br>");
  }

  if (i === 3) break;
}
```

<br>

### continue 사용

특정 조건에서 건너뛰기 (앞으로 돌아가기)

```js
// 짝수끼리 더하기

var i;
var n = 10;
var sum = 0;

for (i = 1; i <= n; i++) {
  if (i % 2 === 1) continue; // 홀수면 건너뛰기
  sum += i;

  document.write(i + "--->" + sum + "<br>");
}
```
