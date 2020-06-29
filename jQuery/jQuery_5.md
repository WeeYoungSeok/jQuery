### jQuery

##### 요소 탐색

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```



- eq() 메서드

```html
<script type="text/javascript">
	$(document).ready(function(){
        $("div > p").eq(0).click(function(){
            $("pre b").eq(0).toggle();
        });
    });
</script>

<pre>
	<b>eq() 메서드</b> : 인덱스로 탐색
</pre>
<div>
    <p>eq()</p>
</div>
```

> .click(function(){})은 사용자가 클릭 이벤트를 발생시켰을때 실행시킬 함수이다.



- slice() 메서드

```html
<script type="text/javascript">
	$(document).ready(function(){
        $("div > p").eq(1).click(function(){
            $("pre b").slice(1,2).toggle();
        });
    });
</script>

<pre>
	<b>slice() 메서드</b> : 인덱스의 길이로 탐색
</pre>
<div>
    <p>slice()</p>
</div>
```

> slice(a,b)는 인덱스를 자르는 것이다.
>
> a에서 b-1까지의 인덱스를 의미함 ( 결국은 1,2는 1번지를 의미 )



- first() 메서드, last() 메서드

  > 메서드의 이름과 같이 가장 처음에 있는 인덱스를 찾는 것이고, 가장 마지막의 인덱스를 찾는 것이다.

```javascript
$(document).ready(function(){
   $("div > p").eq(2).click(function(){
      $("pre b").first().css("color","red").text("굳"); 
   });
});

// end는 first자리에 end()
```



- find("selector") 메서드

  > 선택한 엘리먼트의 자손들 중에 탐색

```html
<pre>
	<b>find("selector") : 선택한 엘리먼트의 자손들 중에 탐색</b>
</pre>
<div>
		<p><b>1</b></p>
</div>
```

```javascript
$(document).ready(function(){
   $("div").find("b").css({"font-size" : "50px", "color", "orangered"}); 
});
```



- children("selector") 메서드

  > 선택한 엘리먼트의 자식들 중에 탐색

```html
<pre>
	<b>children("selector") : 선택한 엘리먼트의 자식들 중에 탐색</b>
</pre>
<div>
	<p id="chd">2</p>
</div>
```

```javascript
$(document).ready(function(){
	   $("div").children("#chd").text("children() 메서드");
    	// div자식중 아이디가 chd인 자식
});
```





- parent() / parents("selector") 메서드

  > 선택한 엘리먼트의 부모 / 조상 탐색

```html
<pre>
	<b>parent() / parents("selector") : 선택한 엘리먼트의 부모 / 조상 탐색</b>
</pre>
<div>
	<p>3</p>
    <p>4</p>
</div>
```

```javascript
$(document).ready(function(){
   $("p").parent().css("background-color","skyblue");
    // p의 부모 즉 div
   $("p > b").parents("div").css("background-color","dodgerblue");
    // p의 자식 b가 가지고있는 부모중 div
});
```



- next("selector") 메서드

  > 선택한 엘리먼트 다음 요소 선택

```html
<pre>
	<b>next("selector") : 선택한 엘리먼트 다음 요소 탐색</b>
</pre>
<div>
    <p>5</p>
    <p>4</p>
    <!-- 4가 바뀜 -->
</div>
```

```javascript
$(document).ready(function(){
    $("p").eq(0).next().css({"font-size" : "30px" , "color":"lightyellow"});
    // p의 0번지 다음 p를 의미
    // 4가 바뀜 lightyellow로 
});
```



- add() 메서드

  > 선택한 엘리먼트에 추가적으로 selector 표현식 작성

```html
<div>
      <p>add()</p>
      <span>선택한 엘리먼트에 추가적으로 selector 표현식 작성</span>
</div>
```

```javascript
$(function(){
   $("p:eq(0)").add("span").css("color", "dodgerblue");
    // p의 0번지를 선택하고 추가적으로 다음에 있는 span태그 선택
    // 둘다 바뀜
    
    $("div").children().click(function(){
       if($(this).prop("tagName")=="SPAN"){
    	  // 사용자가 클릭한것이 div태그의 자식중 span태그라면
          alert("span 클릭!");
          $(this).css("color","darkblue");
       }
});
```

> add는 추가적으로 선택이라 선택한 두가지가 모두 바뀜



- is() 메서드

  > 선택한 엘리먼트가 원하는 엘리먼트가 맞는지 틀리는지

```html
<div>
      <p>add()</p>
      <span>선택한 엘리먼트에 추가적으로 selector 표현식 작성</span>
      <p>is()</p>
      <b>선택한 엘리먼트 중에 구하는 엘리먼트가 있는지 확인</b>
</div>
```

```javascript
$(function(){
	$("div").children().click(function(){
      if($(this).is("p")){
          // div자식들중 사용자가 클릭한것이 p태그라면
          $(this).css("background-color","hotpink");
       }
       if($(this).is("b")) {
 		  // div자식들중 사용자가 클릭한것이 b태그라면
    	   $("p:eq(0)").add("span").css("color","dodgerblue");
    	   $("div").children().css("background-color","");
       }
    });
});
```

> is 메서드는 흔히 쓰이는 맞냐아니냐를 뜻하는 것이다. ( is이면 그 것 )



***이러한 기능으로 DOM탐색을 통해 여러가지 기능을 만들 수 있다.***