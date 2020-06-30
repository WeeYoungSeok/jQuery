### jQuery

##### siblings

> siblings란 선택된 태그의 형제들을 의미 ( 같은 태그들 )

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```

```css
img{
		width: 200px;
		height: 200px;
	}
	
	.addSize{
		width: 300px;
		height: 300px;
	}
	
	.onOffImg{
		display: none;
	}
```

```html
<p>메뉴 만들기</p>

	<ul type="square" class="main_menu">
		<li class="sub_menu1"><b>(1)CSS 셀렉터</b>
			<ul type="circle" class="sub_menu2">
				<li>tag로 선택</li>
				<li>id로 선택</li>
				<li>class로 선택</li>
				<li>parent child로 선택</li>
				<li>parent &gt; child로 선택</li>
				<li>:nth-child(n/even/odd)로 선택</li>
				<li>first-child로 선택</li>
				<li>last-child로 선택</li>
			</ul>
		</li>
		<li class="sub_menu1"><b>(2)속성 셀렉터</b>
			<ul type="circle" class="sub_menu2">
				<li>[attr]</li>
				<li>[attr=value]</li>
				<li>[attr!=value]</li>
				<li>...</li>			
			</ul>
		</li>
		<li class="sub_menu1"><b>(3)폼 셀렉터</b>
			<ul type="circle" class="sub_menu2">
				<li>:input type</li>
			</ul>
		</li>
		<li class="sub_menu1"><b>(4)사용자 정의 셀렉터</b>
			<ul type="circle" class="sub_menu2">
				<li>:eq(n)</li>
				<li>:first</li>
				<li>:last</li>
				<li>:even</li>
				<li>:odd</li>
				<li>:parent</li>
			</ul>
		</li>
	</ul>
```

```javascript
$(function(){
		$("b").click(function(){
			
			$(this).next().slideToggle();
			$(this).parent().siblings().find("ul").slideUp();
			// 여기서 부모(parent)의 형제(siblings)의 자식(children)으로하면 b들까지 닫혀서 b			   가 안보이게됨
			// find로 ul을 찾아줘야함
			
			// b클릭했을때 b자신의 다음에있는 요소를 슬라이드토글해주고
			// 자기자신 b를 눌렀을때 자기의 부모의 모든 형제에게 있는 ul을 slideUp()해주자
				
			// 이걸 도대체 어떻게 찾아서 해주냐?? DOM 탐색 때문이다!
			
			
		});
	});
```

> 개발할때 children 기능은 잘 안쓰게되지만 siblings, parent는 정말 많이 쓰이므로 잘 익혀두자.



##### 클래스 속성 추가하기

```css
img{
		width: 200px;
		height: 200px;
	}
	
	.addSize{
		width: 300px;
		height: 300px;
	}
	
	.onOffImg{
		display: none;
	}
```

```html
<button id="btn">이미지 on/off</button>
	<br/>
	<img alt="image00" src="resources/image/image00.jpg" title="이미지0번"/>
	<img alt="image01" src="resources/image/image01.jpg" title="이미지1번"/>
	<img alt="image02" src="resources/image/image02.jpg" title="이미지2번"/>
```

```javascript
$(function(){
		$("#btn").click(function(){
			$("img").toggleClass("onOffImg");
		});
		
		$("img").click(function(){
			if($(this).hasClass("addSize")) {
				// hasClass(a)는 내가 클릭한녀석이 a라는 클래스를 가지고 있냐
				$(this).removeClass("addSize").attr("title","이미지 축소됨");
				// removeClass(a)는 그 태그가 가지고있는 클래스 a를 삭제해주자
			} else {
				$(this).addClass("addSize").attr("title","이미지 확대됨");
				// addClass는 removeClass와 반대
			}
		});
	});
```

> attr로 속성을 추가해주고 css적어놓은 적용 값도 클래스로 추가해 가져올 수 있다.
>
> 실제 개발자도구( f12 )를 켜보고 확인해보면 img태그에 실제로 추가가되고 삭제가 된다.
>
> **실제 html에 추가하는 기능도 자주 사용하니 잘 익혀두자**