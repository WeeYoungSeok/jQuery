### jQuery

##### 요소 탐색

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js"></script>
```



- eq() 메서드

```html
<script type="text/javascript">
	$(function(){
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
	$(function(){
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