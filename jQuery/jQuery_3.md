### jQuery

##### 이미지에 여러가지 속성 적용

```HTML
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```

```css
img{
    width: 100px;
    height: 100px;
}
```

```html
<table>
		<tr>
		<td><img src="resources/image/image00.jpg" title="image00" id="selId"></td>
		<td><img src="resources/image/image00.jpg" title="image01"></td>
		<td><img src="resources/image/image00.jpg" title="image02" class="selClass"></td>
		<td><img src="resources/image/image00.jpg" title="image03" class="selClass"></td>
		</tr>
    
		<tr>
		<td><img src="resources/image/image00.jpg" title="image04" id="selId"></td>
		<td><span><img src="resources/image/image00.jpg" title="image05"></span></td>
		<td><span><img src="resources/image/image00.jpg" title="image06" class="selClass"></span></td>
		<td><img src="resources/image/image00.jpg" title="image07" class="selClass"></td>
		</tr>
	</table>
```



- 이미지 크기 변경

```html
<script type="text/javascript">
	function resizeImg(){
        $("img").css({"width":"200px","height":"200px"});
    }
</script>

<h1>이미지 크기 200px * 200px로 변경</h1>
<button onclick="resizeImg();">클릭</button>
```



- 이미지 숨기기(css 선택자 이용)

```html
<script type="text/javascript">
	function idSelector(){
        $("#selId").hide();
    }
 
   	function classSelector() {
		$(".selClass").css({"opacity":"0.5"});
	}
    
    function propImg() {
		$("img[title*=02]").slideUp(2000);
	}
</script>

<h1>이미지들 중 id가 'selId'인 이미지 숨기기</h1>
<button onclick="idSelector();">클릭</button>

<h1>이미지들 중 class가 'selClass'인 이미지 투명도 50% 적용</h1>
<button onclick="classSeletor();">클릭</button>

<h1>이미지들 중 속성값으로 탑색하여 slideUp 적용</h1>
<p>
	(title 속성값 중, '02'를 포함하는 img 태그를 찾아서 적용)<br/>
	(slideUp은 2초로 적용)
</p>
<button onclick="propImg();">클릭!</button>
```

> css선택자중 id선택자를 사용해 이미지를 찾고 .hide()로 숨길 수 있다.
>
> $("#selId").css("display","none")로도 가능하다.
>
>  
>
> css선택자중 class선태자를 사용해 이미지를 찾고 투명도 50%를 적용
>
>  
>
> css선택자중 속성선택자를 사용해 이미지를 찾고 slideUp기능 적용
>
> slideUp은 이미지가 서서히 접히면서 사라지게 된다.
>
> slideUp(second)의 second는 밀리세컨드를 의미한다. ( 기본값 400 )



- 이미지 바꾸기

```html
<script type="text/javascript">
    function changeImg() {
		var td1 = document.getElementsByTagName("td");
		for(var i = 0; i < td1.length; i++) {
			$("img[title=image0"+i+"]").prop("src","resources/image/image0"+i+".jpg");
		}
    }
</script>

<h1>5.이미지 바꾸기</h1>
<p>
	(td의 자식요소인 img만 선택해서 바꾸자)
</p>
<button onclick="changeImg();">클릭!</button>
```

> 이미지가 td태그에 둘러 쌓여있다.
>
> 그래서 td태그를 찾아서 그 길이만큼 반복한다. ( img 태그 찾아서 img태그 길이만큼 반복도 가능 )
>
> for문을 통해 img의 title값을 찾아가 그 img태그의 src를 바꾸어주는 코드이다.





