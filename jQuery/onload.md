### jQuery

##### jQuery에서의 onload



- onload란?

  > js에서의 onload.window와 같은 기능이다.
  >
  > 먼저 html의 문서를 전부 읽어 들인 후에 함수를 실행한다.
  >
  > 왜? 그렇게 해야하냐?
  >
  > 이유는 우리가 script를 외부에서 가져오거나 head와 title사이에 작성할 경우 onload없이 작성을 하면 html문서가 맨 윗줄부터 순차적으로 읽어 내려온다.
  >
  > 개발자가 script문을 body부분 위에 썻을 경우 body부분의 태그를 가져올때 먼저 script부분이 실행이되는데 body부분에 도착을 하지도 않았는데 body부분의 태그들을 찾으려고하면 찾아지지 않는다.
  >
  > 이러한 이유때문에 onload로 먼저 문서를 전부 읽어들인 후에 태그들을 찾는다 이렇게하면 script부분을 어느부분에 작성하더라도 태그들을 잘 찾는다.



***js에서의 onload.window는 jq에서는 $(document).ready(function(){}), $(function(){})이 있다.***



```javascript
$(function(){
   // 작성 
});

$(document).ready(function(){
   // 작성 
});
```

