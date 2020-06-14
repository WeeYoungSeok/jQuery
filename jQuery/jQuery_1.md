# jQuery

##### jquery 기본 작성법

- css selector(표현식) + javascript

  > $("selector").메서드();

  ```javascript
  $("p").css("color", "red");
  ```



- 기능 구현 방법

  > ```javascript
  > $(function(){
  >     //작성
  > });
  > ```
  >
  > ```javascript
  > $(document).ready(function(){
  >     //작성
  > });
  > ```



- 셀렉터 표현식

```html
<ul id="list01">
		<li>1.셀렉터 표현식</li>
		<li>2.DOM 탐색 메서드</li>
		<li>3.이벤트 메서드</li>
		<li>4.이펙트 메서드</li>
		<li>5.ajax</li>
	</ul>
	<button onclick="highLight();">리스트 강조하기~!</button>
```

```javascript
function highLight() {
    $("#list > li").eq[0].css("background-color", "red");
}
```

> css selector + javascript방식이다.
>
> eq는 js에서 Elements로 가져왔을때 배열이라고 생각하면 된다.
>
> eq[0]의 경우에는 li태그중 첫번째것을 의미한다.
>
> 버튼을 누르면 1.셀렉터 표현식 글씨에 배경색으로 red가 입혀진다.



```html
	<button onclick="showImg();">이미지 보이기</button>
	<button onclick="resizeImg();">이미지 축소</button>
	<button onclick="addImg();">이미지 추가</button>
	<button onclick="toggleImg();">이미지 숨기기/보이기</button>

<br/><br/><br/><br/>
	
	<div>
		<img alt="test" src="resources/image/image00.jpg"/>
	</div>
```

```javascript
$(function(){
    $("img").click(function(){
        alert("이미지를 클릭했습니다.");
        $(this).hide();
    });
});
```

> 코드를 보면 img 즉 이미지를 클릭시 함수가 실행된다.
>
> 실행되면 경고창 "이미지를 클릭했습니다."가 뜬다.
>
> 그 뒤에 $(this)는 현재 이미지 자기 자신을 의미한다 hide는 내가 선택한 태그를 숨겨주는 역할을 한다.



```javascript
function showImg() {
    $("img").show();
}
```

> hide와 반대로 내가 지정한 태그를 보야준다.



```javascript
function resizeImg() {
    $("img").css("width", "100px").css("height", "100px");
    //$("img").css({"width" : "100px", "height" : "100px"});
}
```

> 이미지의 크기를 바꾸어준다.



```javascript
function addImg() {
    $("img").last().after("<img src='resources/image/image00.jpg'/>")
}
```

> 처음에 만들어진 이미지 뒤에 이미지를 추가하는 방법이다.



```javascript
function toggleImg() {
    $("img").toggle();
}
```

> 이미지를 숨겼다 보였다를 반복할 수 있게 해준다.





