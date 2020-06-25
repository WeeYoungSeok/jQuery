### jQuery



##### jq란?

> 자바스크립트 라이브러리이다.
>
> 처음에는 jquery가 많이 사용이 안되었는데 사용자들이 이용하다보니 너무 편리하고 쉽게 이용할 수 잉서어 기능들을 추가하다보니 무거워졌다.



javascript library

> 다양한 사람들이 만든 기능들을 배포함 ( javascript 기반 )



```javascript
document.getElementsClassName("continue")[0].innerHTML="Next Step...."; 
```

> 자바스크립트의 구문을

```javascript
$( "button.continue" ).html( "Next Step..." );
```

> 이렇게 jquery로 간단하게 표현이 가능하다.



##### jquery의 버전

- compressed 버전

  > 공백이 아예 없는 버전

- uncompressed 버전

  > 공백 포함 버전

***두 버전의 용량 차이는 대략  4배정도 차이난다.***

**uncompressed 버전은 사용자가 보기 쉽고 커스터마이징 하기 편리**



- jq 연결

```html
<script type="text/javascript" src="resources/js/jquery-3.5.1.min.js">
</script>
```

> jq도 javascript library이기 때문에 외부에서 호출해서 사용한다.

***script 태그 사이에 절대 어떠한 것이 입력해서는 안된다***