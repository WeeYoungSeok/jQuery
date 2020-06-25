### jQuery

##### selector 표현식



- jq연결

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```

- tag로 선택

```html
<script type="text/javascript">
	function answer(){
        $("span").css("color","blue");
        $("#view").text('$("span").css("color","blue");');
        // span태그를 찾아 색을 파란색으로
        // id가 view를 찾아 태그의 텍스트를 내가 써준 텍스트로 바꾸자
    }
</script>

<li><span>tag로 선택</span></li>
<button onclick="answer01();">태그선택(span)</button>
<div id="view"></div>
```

> css선택자는 외워두면 정말 많은 곳에서 사용을 한다.
>
> js,jq에서 전부 활용 가능하니 외워두자.
>
> jq문구를 사용할 수 있었던 이유는 외부에서 jq의 파일을 불러왔기 때문이다.



- id로 선택

```html
<script type="text/javascript">
	function answer02(){
        jQuery("#t1").css("color","pink");
        jQuery("#view").text('jQuery("#t1").css("color","pink");');
        // id로 검색하여 css와 text를 바꾸어줌
    }
</script>

<li id="t1">id로 선택</li>
<button onclick="answer02();">id선택(t1)</button>
<div id="view"></div>
```

> 앞서 배운 css선택자중 id선택자 이용
>
> $는 jQuery로 사용가능



- class로 선택

```html
<script type="text/javascript">
    function answer03() {
		$(".t2").css("color","yellowgreen");
		$("#view").text('$(".t2").css("color","yellowgreen");');
	}
</script>

<li class="t2">class로 선택</li>
<button onclick="answer03();">class선택(t2)</button>
<div id="view"></div>
```

> css선택자중 class선택자 이용



- parent child로 선택

```html
<script type="text/javascript">
function answer04() {
		$("li span").css("color","orangered");
		$("#view").text('$("li > span").css("color","orangered");');
	}
</script>

<li><b><span>parent &gt; child</span></b>로 선택</li>
<button onclick="answer04();">p c 선택</button>
<div id="view"></div>
```

> css선택자중 하위 선택자 이용



- parent > child로 선택

```html
<script type="text/javascript">
	function answer05() {
		$("li > span").css("color","purple");
		$("#view").text('$("li > span").css("color","purple");');
	}
</script>

<li><b><span>parent &gt; child</span></b>로 선택</li>
<button onclick="answer05();">p &gt; c 선택</button>
<div id="view"></div>
```

> css선택자중 자식 선택자 이용



