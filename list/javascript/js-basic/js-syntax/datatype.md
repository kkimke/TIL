## data type

- 기본 유형 : 숫자, 문자열, 논리형
- 복합 유형 : 배열, 객체
- 특수 유형 : undefined, null

<br>

### 숫자형 number

```js
console.log(typeof 100); // number
console.log(typeof 4.13); // number (실수도 동일)
```

js에서 실수를 정밀하게 계산하는 것을 적합하지 않음<br>

```js
0.1 + 0.2; // 0.30000000000000004
```

<br>

### 문자열 string

```js
// 작은따옴표나 큰따옴표는 중복되지 않도록

document.write("<span style='color:blue'>", "Hello", "</span>");
```

<br>

### 논리형 boolean

```js
100 > 10; // true
100 < 10; // false
```

<br>

### 배열 array

하나의 변수에 여러 개의 값을 저장

```js
var r = red;
var g = green;
var b = blue;
```

```js
var rgb = ["red", "green", "blue"];
```

```js
rgb[1]; // green
```

### undefined, null

undefined : 변수 선언만 하고 값이 할당되지 않은 자료형

null : 변수에 할당된 값이 유효하지 않은 상태
