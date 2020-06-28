### jQuery

##### 태그의 value값 가져오기

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```



> 태그들의 벨류값은 그 태그를 찾고 .val()을 통해 가져올 수 있다.
>
> val()은 input 태그의 벨류값을 가져올 수 있다.
>
>  태그들 사이의 text를 가져오고 싶으면 .text로 가져올 수 있다.



```javascript
function c1() {
		var doc = $("input:text").val();
		// input타입의 text인 input의 value를 가져오자
		console.log(doc);
}
```

```html
<input type="text"/>
<input type="button" value="선택" onclick="c1();"/>
```

> 사용자가 텍스트에 입력한 값을 가져온다.



```javascript
$(function(){
		var selElem = document.getElementsByTagName("select")[0];
		selElem.onchange=function() {
			alert(selElem.options[selElem.selectedIndex].value);
		}
});
```

```html
<select>
		<option value="1">one</option>
		<option value="2">two</option>
		<option value="3">three</option>
</select>
```

> onchange는 select의 태그가 변할때 함수가 실행된다.
>
> 변할떄 실행되는 함수는 내가 찍은 option의 value를 가져온다.
>
> selEme.options는 select의 옵션들을 의미하며 배열 형태이다.
>
> 인덱스의 코드는 내가 선택한 번지를 의미한다.

