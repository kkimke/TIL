## event

<br>

## 이벤트 처리 방법

### HTML 태그에 직접 연결

- on + 이벤트 이름 + 함수명

```html
<ul>
  <li>
    <a href="#" onclick="alert('버튼을 클릭했습니다')"> Green </a>
  </li>
</ul>
```

### 함수를 미리 만들어 연결

- changeBg함수를 미리 만들어 색상값은 인자로 넘기기

```html
<ul>
  <li>
    <a href="#" onclick="changeBg('green')"> Green </a>
  </li>
  <li>
    <a href="#" onclick="changeBg('orange')"> Orange </a>
  </li>
</ul>
<div id="result"></div>

<script>
  function changeBg(color) {
    let result = document.querySelector("#result");
    result.style.backgroundColor = color;
  }
</script>
```

### DOM을 이용한 이벤트 처리기

(방법1 : 웹 요소를 변수로 지정 & 미리 만든 함수 사용)

```html
<button id="change">글자색 바꾸기</button>

<script>
  var changeBtn = document.querySelector("#change");
  changeBtn.onclick = changeColor;

  function changeColor() {
    document.querySelector("p").style.color = "#f00";
  }
</script>
```

(방법2 : 변수에 할당하지 않고 직접 사용)

```js
document.querySelecor("#change").onclick = changeColor;

function changeColor() {
  document.querySelector("p").style.color = "#f00";
}
```

(방법3 : 함수를 직접 선언)

```js
document.querySelector("#change").onclick = function () {
  document.querySelector("p").style.color = "#f00";
};
```
