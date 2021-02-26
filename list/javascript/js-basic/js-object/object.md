## object

<br>

### js의 객체

- 문서 객체 모델(DOM): 문서, 문서에 포함된 이미지.링크.텍스트 필드 등을 모두 별도의 객체로 관리
- 브라우저 관련 객체: 웹 브라우저 정보를 객체로 관리
- 내장 객체: 웹 프로그래밍에서 자주 사용하는 요소를 객체로 정의
- 사용자 정의 객체: 필요할때마다 사용자가 객체를 정의

<br>

### 객체의 인스턴스 만들기

- js에서는 객체 자체가 아니라 인스턴스 형태로 만들어서 사용
- 인스턴스 : 객체를 틀처럼 사용하여 같은 모양으로 찍어낸 것
- 형태 - new 객체명

```js
var now = new Date();
document.write("현재 시각은 " + now);

// Date 객체의 인스턴스를 만들어 now 변수에 저장
// now는 Date객체의 모든 성질을 사용 가능
```

<br>

- 프로퍼티 property : 객체의 특징이나 속성
- 메서드 method : 객체에서 할 수 있는 동작

```js
var now = new Date();
document.write("현재 시각은 " + now.toLocaleString());

// Date 객체의 메소드(toLocaleString) 사용
```

<br>

### js 내장객체

[built-in object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)<br>
대표적 : Array객체, Date객체, Math객체 ...

<br>

- Date 객체 인스턴스 만들기

```js
// 현재 날짜로 설정할 경우
new Date();
```

```js
// 특정 날짜로 설정할 경우
new Date("2021-02-25");
```

```js
// 특정 날짜와 시간 나타내기
new Date("2021-02-25T10:00:00");
```

<br>

- Date 객체의 메서드

1. 날짜,시간 가져오는 메서드
2. 원하는 날짜,시간으로 설정하는 메서드
3. 날짜,시간의 형식 바꾸는 메서드로 구분됨

```html
<!-- 날짜계산 프로그램 -->

<p>새해가 <span id="result"></span>일 지났습니다.</p>

<script>
  var now = new Date(); // 오늘날짜를 객체로
  var firstDay = new Date("2021-01-01"); // 시작날짜를 객체로

  var toNow = now.getTime(); // 오늘까지 지난시간 (밀리초)
  var toFirst = firstDay.getTime(); // 첫날까지 지난시간
  var passedTime = toNow - toFirst; // 첫날부터 오늘까지 지난시간

  passedTime = Math.round(passedTime / (24 * 60 * 60 * 1000)); // Math객체 활용-밀리초를 일수로 계산하여 반올림

  document.querySelector("#result").innerText = passedTime;
</script>
```

<br>

- Math 객체

```html
<!-- 당첨자 뽑기 프로그램 -->

<script>
  var total = prompt("전체 응모자 수");
  var pick = Math.floor(Math.random() * total + 1);

  document.write("전체 응모자 수: " + total + "명<br>");
  document.write("당첨자: " + pick + "번");
</script>
```

-random() 메서드 : 무작위 번호 (\*100+1로 1~100 사이 값 출력)<br>
-floor() 메서드 : 소수점 이하 버리기<br>
<br>

### 브라우저 관련 객체

- 웹 브라우저 창에 문서가 표시되는 순간 브라우저는 html소스를 한 줄씩 읽으며 관련된 객체 만듦
- 가장 먼저 window 객체가 만들어지고, 하위 요소의 객체들이 나타남
- 이 하위 객체들(브라우저 요소)은
  가각 다른 하위 객체를 가짐

<br>

- window객체 > document, nevigator, history, location, screen 객체 > ...
- window객체의 메서드인 alert(), prompt() 등을 사용할때는 window를 생략하여 사용

<br>

## 문서 객체 모델(DOM)

- js를 이용하여 웹 문서에 접근하고 제어할 수 있도록 객체를 사용해 웹 문서를 체계적으로 정리하는 방법
- DOM tree : html > head, body > meta, title, h1, img ... 이와 같이 부모와 자식 구조로 표현되는데 마치 나무 형태와 같음
- 이렇게 웹 문서를 해석할 DOM 구조를 머릿 속에 그릴 수 있어야 js로 객체에 접근하여 원하는 부분 수정 가능

<br>

### DOM요소에 접근하여 속성 가져오기

```js
document.getElementById("id");
document.getElementByClassName("class");
document.getElementByTagName("p");
```

```js
document.querySelecotr("#id");
document.querySelectorAll(".class");
```

### 웹 요소의 내용 수정

```js
var now = new Date();

function innertext() {
  document.getElementById("current").innerText = now;
}
```

```js
function innerhtml() {
  document.getElementById("current").innerHTML = "<em>" + now + "</em>";
}
```

### DOM에서 이벤트 처리

```js
var cup = document.querySelector("#cup");
cup.onclick = function () {
  alert("이미지를 클릭했습니다");
};
```

```js
cup.onclick = changePic;

function changePic() {
  cup.src = "images/cup.png";
}
```

### 한 요소에 여러 이벤트 처리기

```
요소.addEventListener("이벤트", 함수, 캡처 여부);
```

```js
var cover = document.getElementById("cover");
cover.addEventListener("mouseover", changePic);  // 포인터 올리면 changePic함수 실행
cover.addEventListener("mouseout", originPic);  // 포인터 내리면 originPic함수 실행

function changePic(){
  ...
}
function originPic(){
  ...
}
```

### CSS속성 접근

```
document.요소명.style.속성명
```

```js
document.getElementById("des").style.color = "blue";
```
