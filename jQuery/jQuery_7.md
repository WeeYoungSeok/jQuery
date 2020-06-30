### jQuery

##### effect

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```

```html
<b>이펙트 메서드</b>
   <div>
      <p>hide()</p>
      <p>show()</p>
      <p>toggle()</p>
      <p>slideUp()</p>
      <p>slideDown()</p>
      <p>slideToggle()</p>
      <p>fadeOut()</p>
      <p>fadeIn()</p>
      <p>fadeTo()</p>
      <p>fadeToggle()</p>
      <p>animate()</p>
   </div>
<img alt="img" src="resources/image/image00.jpg" id="img1"/>
```



- hide()

  > 숨겨주는 기능

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(hide)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").hide();
        }
	});
});
```



- show()

  > 보여주는 기능

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(show)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").show();
        }
	});
});
```



- toggle()

  > 이벤트 발생시 show()와 hide()를 번갈아 씀 ( display에도 적용 됨 ) ( 픽셀에는 영향을 안줌 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(toggle)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").toggle();
        }
	});
});
```



- slideUp()

  > height값을 조절하여 시간만큼 줄어든다 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(slideUp)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").slideUp();
        }
	});
});
```



- slideDown()

  > height값을 조절하여 시간만큼 늘어난다 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(slideDown)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").slideDown();
        }
	});
});
```



- slideToggle() 

  > slideUp,Down이 Toggle형태 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(slideToggle)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").slideToggle();
        }
	});
});
```



- fadeOut()

  > 시간만큼 투명도를 0까지 낮추는 기능 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(fadeOut)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").fadeOut();
        }
	});
});
```



- fadeIn()

  > 시간만큼 투명도이 0인 상태를 투명도 100으로 만드는 기능 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(fadeIn)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").fadeIn();
        }
	});
});
```



- fadeTo(밀리세컨드,투명도)

  > 시간만큼 서서히 투명도를 설정한 값까지 적용시키는 기능 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(fadeTo)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").fadeTo(400,0.2);
            // 400밀리세컨드동안 투명도를 1부터 0.2까지 줄여줌
        }
	});
});
```



- fadeToggle()

  > 토글기능을 적용시켜 시간만큼 투명도가 0에서 다시 1로 적용시키는 기능 ( 기본값 400밀리세컨드 )

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(fadeToggle)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").fadeToggle();
        }
	});
});
```



- animate(적용크기(css),밀리세컨드)

  > 시간만큼 서서히 적용한 css 적용

```javascript
$(function(){
	$("p").bind("click",function(){
		if($(this).is("p:contatins(animate)")){
            // contains : 태그의 텍스트가 괄호안의 문자열을 포함하는지 묻는 기능
            $("img").animate({
                "width" : "500px",
                "height" : "500px",
                "left" : "500px",
                "top" : "0px"
            },2000);
        }
	});
});
```

***자바에서의 메소드체이닝처럼  2000).slideUp()이나 animate를 더 이어붙여서 애니메이션 효과를 줄 수 있다. (크기가 변하면서 움직이는 네모박스 같은것 )***