### jQeury

##### event

```css
div{
		width: 400px;
		height: 200px;
		border: 2px solid blue;
		padding: 20px;
		overflow: auto;
	}
	
	div p:first-child{
		float: left;
		border: 1px solid red;
		width: 150px;
		height: 150px;
		text-align: center;
		line-height: 150px;
	}
	
	div p:last-child{
		float: right;
		border: 1px solid red;
		width: 150px;
		height: 150px;
		text-align: center;
		line-height: 150px;
	}
	a{
		text-decoration: none;
}
```

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```

```html
<span>unbind() : 이벤트 해제</span>
	<div>
		<p>
			<a href="http://www.naver.com">클릭!</a>
		</p>
		<p>클릭!</p>
	</div>
	
	<div>
		<p>
			<a href="http://www.google.com">클릭!</a>
		</p>
		<p>클릭!</p>
	</div>
	<button>요소 추가</button>
```



- 이벤트 전파 막기

  > 이벤트 전파란? 
  >
  > > 각 요소가 서로 포함돤계(중첩)인 경우 요소 중 하나에 이벤트가 발생하면 중첩된 요소들도 이벤트가 전파된다.
  >
  >  
  >
  > 이벤트 전파 막는 방법
  >
  > > stopPropagation() : 이벤트 요소의 전파 막기
  > >
  > > preventDefault() : 이벤트에 의한 기본 동작 막기
  > >
  > > return false : 위의 기능 두개 적용



- stopPropagation()

```javascript
$(function(){
    $("p").click(function(e){
			// e는 이벤트
			alert("p 클릭!");
			e.stopPropagation();
    }):
});
```

> 만약 이 클릭 이벤트 위에 클릭이벤트가 존재한다면 그 클릭이벤트는 실행해줌
>
> 이 클릭 이벤트 아래 이벤트들의 전파는 전부 막음 ( 중첩되어 있을 경우에만 )
>
> 그리고 중첩되어있는 a태그의 href에 있는 링크는 못 막아준다.



- preventDefault() 메서드

> stopPropagation()과 달리 이 시점에 있는 이벤트 밑에 있는 클릭 이벤트도 실행됨 (중첩되어 있을 경우)
>
> 그리고 중첩되어있는 a태그의 href에 있는 링크도 같이 막아준다.

