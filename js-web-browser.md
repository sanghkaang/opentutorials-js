# 웹브라우저와 JavaScript

## HTML

- 정보를 표현한다
```html
<!DOCTYPE html>
<html>
<body>
    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
    </ul>
</body>
</html>
```

## CSS

- 정보를 꾸며준다
```html
<!DOCTYPE html>
<html>
<head>
    <style type="text/css">
        #selected{
            color:red;
        }
    </style>
</head>
<body>
    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li id="selected">JavaScript</li>
    </ul>
</body>
</html>
```

## JavaScript

- HTML을 프로그래밍적으로 제어한다.
```html
<!DOCTYPE html>
<html>
<head>
    <style type="text/css">
        #selected{
            color:red;
        }
        .dark {
            background-color:black;
            color:white;
        }
        .dark #selected{
            color:yellow;
        }
    </style>
</head>
<body>
    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li id="selected">JavaScript</li>
    </ul>
    <input type="button" onclick="document.body.className='dark'" value="dark" />
</body>
</html>
```

# 실습방법
- 크롬 개발자 도구
- texteditor(sublime text, vs code, atom...)

# HTML에서 JavaScript 로드하기

## inline

inline 방식은 태그에 직접 자바스크립트를 기술하는 방식이다. 장점은 태그에 연관된 스크립트가 분명하게 드러난다는 점이다. 하지만 정보와 제어가 섞여 있기 때문에 정보로서의 가치가 떨어진다.
```html
<!DOCTYPE html>
<html>
<body>
    <input type="button" onclick="alert('Hello world')" value="Hello world" />
</body>
</html>
```

## script

태그를 만들어서 여기에 자바스크립트 코드를 삽입하는 방식이다. 장점은 html 태그와 js 코드를 분리할 수 있다는 점이다. 

```html
<!DOCTYPE html>
<html>
<body>
    <input type="button" id="hw" value="Hello world" />
    <script type="text/javascript">
        var hw = document.getElementById('hw');
        hw.addEventListener('click', function(){
            alert('Hello world');
        })
    </script>
</body>
</html>
```

## 외부 파일로 분리

js를 별도의 파일로 분리할 수도 있다. 장점은 보다 엄격하게 정보와 제어를 분리할 수 있다. 하나의 js 파일을 여러 웹페이지에서 로드함으로서 js의 재활용성을 높일 수 있다. 캐쉬를 통해서 속도의 향상, 전송량의 경량화를 도모할 수 있다.

```html
<!DOCTYPE html>
<html>
<body>
    <input type="button" id="hw" value="Hello world" />
    <script type="text/javascript" src="script2.js"></script>
</body>
</html>
```

```js
// script2.js
var hw = document.getElementById('hw');
hw.addEventListener('click', function(){
    alert('Hello world');
})
```

## Script 파일의 위치

script를 head 태그에 위치시킬 수도 있다. 하지만 이 경우는 오류가 발생한다.

```html
<!DOCTYPE html>
<html>
<head>
    <script src="script2.js"></script>
</head>
<body>
    <input type="button" id="hw" value="Hello world" />
</body>
</html>
```

아래와 같이 script2.js의 코드를 수정해야 한다.

```js
window.onload = function(){
    var hw = document.getElementById('hw');
    hw.addEventListener('click', function(){
        alert('Hello world');
    })
}
```

window.onload = function(){} 함수는 웹브라우저의 모든 구성요소에 대한 로드가 끝났을 때 브라우저에 의해서 호출되는 함수다. 이러한 것을 이벤트라고 하는데 이벤트는 뒤에서 배울 것이다.

> script 파일은 head 태그 보다 페이지의 하단에 위치시키는 것이 더 좋은 방법이다. *header에 하면 렌더링이 느리니까*

# Object Model

웹브라우저의 구성요소들은 하나하나가 객체화되어 있다. 자바스크립트로 이 객체를 제어해서 웹브라우저를 제어할 수 있게 된다. 이 객체들은 서로 계층적인 관계로 구조화되어 있다. BOM과 DOM은 이 구조를 구성하고 있는 가장 큰 틀의 분류라고 할 수 있다.

## JavaScript Core

JavaScript 언어 자체에 정의되어 있는 객체들(Object, Array, Function ...)

## BOM

Browser Object Model. 웹페이지의 내용을 제외한 브라우저의 각종 요소들을 객체화시킨 것이다. 전역객체 Window의 프로퍼티에 속한 객체들이 이에 속한다. 

## DOM

Document Object Model. 웹페이지의 내용을 제어한다. window의 프로퍼티인 document 프로퍼터에 할당된 Document 객체가 이러한 작업을 담당한다. 
Document 객체의 프로퍼티는 문서 내의 주요 엘리먼트에 접근할 수 있는 객체를 제공한다.

# BOM

BOM(Browser Object Model)이란 웹브라우저의 창이나 프래임을 추상화해서 프로그래밍적으로 제어할 수 있도록 제공하는 수단이다. BOM은 전역객체인 Window의 프로퍼티와 메소드들을 통해서 제어할 수 있다. 따라서 BOM에 대한 수업은 Window 객체의 프로퍼티와 메소드의 사용법을 배우는 것이라고 해도 과언이 아닐 것이다. 본 토픽의 하위 수업에서는 Window 객체의 사용법을 알아볼 것이다.

## 전역객체 Window

### Window 객체

Window 객체는 모든 객체가 소속된 객체이고, 전역객체이면서, 창이나 프레임을 의미한다. 

### 전역객체

Window 객체는 식별자 window를 통해서 얻을 수 있다. 또한 생략 가능하다. Window 객체의 메소드인 alert을 호출하는 방법은 아래와 같다.

```html
<!DOCTYPE html>
<html>
<script>
    alert('Hello world');
    window.alert('Hello world');
</script>
<body>
</body>
</html>
```

아래는 전역변수 a에 접근하는 방법이다.  
```html
<!DOCTYPE html>
<html>
<script>
    var a = 1;
    alert(a);
    alert(window.a);
</script>
<body>
</body>
</html>
```
객체를 만든다는 것은 결국 window 객체의 프로퍼티를 만드는 것과 같다.
```html
<!DOCTYPE html>
<html>
<script>
    var a = {id:1};
    alert(a.id);
    alert(window.a.id);
</script>
<body>
</body>
</html>
```
예제를 통해서 알 수 있는 것은 전역변수와 함수가 사실은 window 객체의 프로퍼티와 메소드라는 것이다. 또한 모든 객체는 사실 window의 자식이라는 것도 알 수 있다. 이러한 특성을 ECMAScript에서는 Global 객체라고 부른다. ECMAScript의 Global 객체는 호스트 환경에 따라서 이름이 다르고 하는 역할이 조금씩 다르다. 웹브라우저 자바스크립트에서 Window 객체는 ECMAScript의 전역객체이면서 동시에 웹브라우저의 창이나 프레임을 제어하는 역할을 한다.

## 사용자와 커뮤니케이션 하기

HTML은 form을 통해서 사용자와 커뮤니케이션할 수 있는 기능을 제공한다. 자바스크립트에는 사용자와 정보를 주고 받을 수 있는 간편한 수단을 제공한다. 

### alert

경고창이라고 부른다. 사용자에게 정보를 제공하거나 디버깅등의 용도로 많이 사용한다.
```html
<!DOCTYPE html>
<html>
    <body>
        <input type="button" value="alert" onclick="alert('hello world');" />
    </body>
</html>
```

### confirm

확인을 누르면 true, 취소를 누르면 false를 리턴한다.
```html
<!DOCTYPE html>
<html>
    <body>
        <input type="button" value="confirm" onclick="func_confirm()" />
        <script>
            function func_confirm(){
                if(confirm('ok?')){
                    alert('ok');
                } else {
                    alert('cancel');
                }
            }
        </script>
    </body>
</html>
```

### prompt

```html
<!DOCTYPE html>
<html>
    <body>
        <input type="button" value="prompt" onclick="func_prompt()" />
        <script>
            function func_prompt(){
                if(prompt('id?') === 'egoing'){
                    alert('welcome');
                } else {
                    alert('fail');
                }
            }
        </script>
    </body>
</html>
```

## Location 객체

Location 객체는 문서의 주소와 관련된 객체로 Window 객체의 프로퍼티다. 이 객체를 이용해서 윈도우의 문서 URL을 변경할 수 있고, 문서의 위치와 관련해서 다양한 정보를 얻을 수 있다.

### 현재 윈도우의 URL 알아내기

`console.log(location.toString(), location.href);`

### URL Parsing

location 객체는 URL을 의미에 따라서 별도의 프로퍼티로 제공하고 있다. 

`console.log(location.protocol, location.host, location.port, location.pathname, location.search, location.hash)`

### URL 변경하기

아래 코드는 현재 문서를 http://egoing.net으로 이동한다.
`location.href = 'http://egoing.net';`
아래와 같은 방법도 같은 효과를 낸다.
`location = 'http://egoing.net';`
아래는 현재 문서를 리로드하는 간편한 방법을 제공한다.
`location.reload();  //location.href=location.href 같은 효과`

## Navigator 객체

브라우저의 정보를 제공하는 객체다. 주로 호환성 문제등을 위해서 사용한다.
`console.dir(navigator);` 명령을 통해서 이 객체의 모든 프로퍼티를 열람할 수 있다.

### appName

웹브라우저의 이름이다. IE는 Microsoft Internet Explorer, 파이어폭스, 크롬등은 Nescape로 표시한다.

### appVersion

브라우저의 버전을 의미한다.

### userAgent

브라우저가 서버측으로 전송하는 USER-AGENT HTTP 헤더의 내용이다. appVersion과 비슷하다.

### platform

브라우저가 동작하고 있는 운영체제에 대한 정보다.

### 기능테스트

Navigator 객체는 브라우저 호환성을 위해서 주로 사용하지만 모든 브라우저에 대응하는 것은 쉬운 일이 아니므로 아래와 같이 기능 테스트를 사용하는 것이 더 선호되는 방법이다. 

예를 들어 Object.keys라는 메소드는 객체의 key 값을 배열로 리턴하는 Object의 메소드다. 이 메소드는 ECMAScript5에 추가되었기 때문에 오래된 자바스크립트와는 호환되지 않는다. 아래의 코드를 통해서 호환성을 맞출 수 있다. 

```js
// From https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys
if (!Object.keys) {
  Object.keys = (function () {
    'use strict';
    var hasOwnProperty = Object.prototype.hasOwnProperty,
        hasDontEnumBug = !({toString: null}).propertyIsEnumerable('toString'),
        dontEnums = [
          'toString',
          'toLocaleString',
          'valueOf',
          'hasOwnProperty',
          'isPrototypeOf',
          'propertyIsEnumerable',
          'constructor'
        ],
        dontEnumsLength = dontEnums.length;
 
    return function (obj) {
      if (typeof obj !== 'object' && (typeof obj !== 'function' || obj === null)) {
        throw new TypeError('Object.keys called on non-object');
      }
 
      var result = [], prop, i;
 
      for (prop in obj) {
        if (hasOwnProperty.call(obj, prop)) {
          result.push(prop);
        }
      }
 
      if (hasDontEnumBug) {
        for (i = 0; i < dontEnumsLength; i++) {
          if (hasOwnProperty.call(obj, dontEnums[i])) {
            result.push(dontEnums[i]);
          }
        }
      }
      return result;
    };
  }());
}
```

## 창 제어

window.open 메소드는 새 창을 생성한다. 현대의 브라우저는 대부분 탭을 지원하기 때문에 window.open은 새 창을 만든다. 아래는 메소드의 사용법이다.

```html
<!DOCTYPE html>
<html>
<style>li {padding:10px; list-style: none}</style>
<body>
<ul>
    <li>
        첫번째 인자는 새 창에 로드할 문서의 URL이다. 인자를 생략하면 이름이 붙지 않은 새 창이 만들어진다.<br />
        <input type="button" onclick="open1()" value="window.open('demo2.html');" />
    </li>
    <li>
        두번째 인자는 새 창의 이름이다. _self는 스크립트가 실행되는 창을 의미한다.<br />
        <input type="button" onclick="open2()" value="window.open('demo2.html', '_self');" />
    </li>
    <li>
        _blank는 새 창을 의미한다. <br />
        <input type="button" onclick="open3()" value="window.open('demo2.html', '_blank');" />
    </li>
    <li>
        창에 이름을 붙일 수 있다. open을 재실행 했을 때 동일한 이름의 창이 있다면 그곳으로 문서가 로드된다.<br />
        <input type="button" onclick="open4()" value="window.open('demo2.html', 'ot');" />
    </li>
    <li>
        세번재 인자는 새 창의 모양과 관련된 속성이 온다.<br />
        <input type="button" onclick="open5()" value="window.open('demo2.html', '_blank', 'width=200, height=200, resizable=yes');" />
    </li>
</ul>
 
<script>
function open1(){
    window.open('demo2.html');
}
function open2(){
    window.open('demo2.html', '_self');
}
function open3(){
    window.open('demo2.html', '_blank');
}
function open4(){
    window.open('demo2.html', 'ot');
}
function open5(){
    window.open('demo2.html', '_blank', 'width=200, height=200, resizable=no');
}
</script>
</body>
</html>
```

### 새 창에 접근

아래 예제는 보안상의 이유로 실제 서버에서만 동작하고, 같은 도메인의 창에 대해서만 작동한다.

```html
<!DOCTYPE html>
<html>
<body>
    <input type="button" value="open" onclick="winopen();" />
    <input type="text" onkeypress="winmessage(this.value)" />
    <input type="button" value="close" onclick="winclose()" />
    <script>
    function winopen(){
        win = window.open('demo2.html', 'ot', 'width=300px, height=500px');
    }
    function winmessage(msg){
        win.document.getElementById('message').innerText=msg;
    }
    function winclose(){
        win.close();
    }
    </script>
</body>
</html>
```

### 팝업 차단

사용자의 인터렉션이 없이 창을 열려고 하면 팝업이 차단된다.
대부분의 웹브라우저가 팝업을 차단한다.
위의 예제는 버튼을 눌리는 인터렉션이 있는 경우이다.

```html
<!DOCTYPE html>
<html>
<body>
    <script>
    window.open('demo2.html');
    </script>
</body>
</html>
```

# DOM

Document Object Model로 웹페이지를 자바스크립트로 제어하기 위한 객체 모델을 의미한다. window 객체의 document 프로퍼티를 통해서 사용할 수 있다. *Window 객체가 창을 의미한다면 Document 객체는 윈도우에 로드된 문서를 의미한다고 할 수 있다.* DOM의 하위 수업에서는 문서를 제어하는 방법에 대한 내용을 다룬다. 

## 제어 대상을 찾기

문서를 자바스크립트로 제어하려면 제어의 대상에 해당되는 객체를 찾는 것이 제일 먼저 할 일이다. 문서 내에서 객체를 찾는 방법은 document 객체의 메소드를 이용한다. 

### document.getElementsByTagName

getElementsByTagName은 인자로 전달된 태그명에 해당하는 객체들을 찾아서 그 리스트를 NodeList라는 유사 배열에 담아서 반환한다. NodeList는 배열은 아니지만 length와 배열접근연산자를 사용해서 엘리먼트를 조회할 수 있다.

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
<script>
    var lis = document.getElementsByTagName('li');
    for(var i=0; i < lis.length; i++){
        lis[i].style.color='red';   
    }
</script>
</body>
</html>
```

만약 조회의 대상을 좁히려면 아래와 같이 특정 객체를 지정하면 된다. 이러한 원칙은 다른 메소드에도 적용된다.

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
<script>
    var ul = document.getElementsByTagName('ul')[0];
    var lis = ul.getElementsByTagName('li');
    for(var i=0; lis.length; i++){
        lis[i].style.color='red';   
    }
</script>
</body>
</html>
```

### document.getElementsByClassName

class 속성의 값을 기준으로 객체를 조회할수도 있다

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li class="active">CSS</li>
    <li class="active">JavaScript</li>
</ul>
<script>
    var lis = document.getElementsByClassName('active');
    for(var i=0; i < lis.length; i++){
        lis[i].style.color='red';   
    }
</script>
</body>
</html>
```

### document.getElementById

s가 안붙는다 하나의 값만 리턴
id 값을 기준으로 객체를 조회한다. 성능면에서 가장 우수하다.

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li id="active">CSS</li>
    <li>JavaScript</li>
</ul>
<script>
    var li = document.getElementById('active');
    li.style.color='red';
</script>
</body>
</html>
```

### document.querySelector

css 선택자의 문법을 이용해서 객체를 조회할수도 있다.

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
<ol>
    <li>HTML</li>
    <li class="active">CSS</li>
    <li>JavaScript</li>
</ol>
 
<script>
    var li = document.querySelector('li');
    li.style.color='red';
    var li = document.querySelector('.active');
    li.style.color='blue';
</script>
</body>
</html>
```

### document.querySelectorAll

querySelector과 기본적인 동작방법은 같지만 모든 객체를 조회한다는 점이 다르다.

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
<ol>
    <li>HTML</li>
    <li class="active">CSS</li>
    <li>JavaScript</li>
</ol>
 
<script>
    var lis = document.querySelectorAll('li');
    for(var name in lis){
        lis[name].style.color = 'blue';
    }
</script>
</body>
</html>
```

## jQuery

### 라이브러리

자주 사용하는 로직을 재사용할 수 있도록 고안된 소프트웨어를 라이브러리라고 한다.

### jQuery

jQuery는 DOM을 내부에 감추고 보다 쉽게 웹페이지를 조작할 수 있도록 돕는 도구이다. jQuery의 효용은 후속 수업을 통해서 살펴보자.

### jQuery의 사용

```html
<!DOCTYPE html>
<html>
<body>
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
    <script>
    jQuery( document ).ready(function( $ ) {
      $('body').prepend('<h1>Hello world</h1>');
    });
    </script>
</body>
</html>
```

## 제어 대상을 찾기 (jQuery)

jQuery를 이용하면 DOM을 사용하는 것 보다 훨씬 효율적으로 필요한 객체를 조회할 수 있다. jQuery는 객체를 조회할 때 CSS 선택자를 이용한다.

### jQuery의 기본문법

`$('li').css('color', 'red');`
$()는 jQuery의 함수이다. 이 함수의 인자로 CSS 선택자(li)를 전달하면 jQuery 객체라는 것을 리턴한다. 이 객체는 선택자에 해당하는 엘리먼트를 제어하는 다양한 메소드를 가지고 있다. 위의 그림에서 css는 선택자에 해당하는 객체들의 style에 color:red로 변경한다.

### jQuery 사용 예제

```html
<!DOCTYPE html>
<html>
<head>
    <style>
    #demo{width:200px;float: left; margin-top:120px;}
    #execute{float: left; margin:0; font-size:0.9em;}
    #execute{padding-left: 5px}
    #execute li{list-style: none}
    #execute pre{border:1px solid gray; padding:10px;}
    </style>
</head>
<body>
<ul id="demo">
    <li class="active">HTML</li>
    <li id="active">CSS</li>
    <li class="active">JavaScript</li>
</ul>
<ul id="execute">
    <li>
        <pre>
var lis = document.getElementsByTagName('li');
for(var i=0; i&lt;lis.length; i++){
    lis[i].style.color='red';   
</pre>
        <pre>
$('li').css('color', 'red')     </pre>
        <input type="button" value="execute" onclick="$('li').css('color', 'red')" />
    </li>
    <li>
        <pre>
var lis = document.getElementsByClassName('active');
for(var i=0; i &lt; lis.length; i++){
    lis[i].style.color='red';   
}</pre>
        <pre>
$('.active').css('color', 'red')</pre>
        <input type="button" value="execute" onclick="$('.active').css('color', 'red')" />
    </li>
    <li>
        <pre>
var li = document.getElementById('active');
li.style.color='red';
li.style.textDecoration='underline';</pre>
        <pre>
$('$active').css('color', 'red').css('textDecoration', 'underline');
        </pre>
        <input type="button" value="execute" onclick="$('#active').css('color', 'red').css('textDecoration', 'underline')" />
    </li>
</ul>
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
</body>
</html>
```

## HTMLElement

### HTMLElement

getElement* 메소드를 통해서 원하는 객체를 조회했다면 이 객체들을 대상으로 구체적인 작업을 처리해야 한다. 이를 위해서는 획득한 객체가 무엇인지 알아야 한다. 그래야 적절한 메소드나 프로퍼티를 사용할 수 있다.

아래 코드는 getElement*의 리턴 값을 보여준다. 

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li id="active">JavaScript</li>
</ul>
<script>
    var li = document.getElementById('active');
    console.log(li.constructor.name);
    var lis = document.getElementsByTagName('li');
    console.log(lis.constructor.name);
</script>

<!-- 실행결과
HTMLLIElement 
HTMLCollection -->
```
이것을 통해서 알 수 있는 것은 아래와 같다.
- document.getElementById : 리턴 데이터 타입은 HTMLLIELement
- document.getElementsByTagName : 리턴 데이터 타입은 HTMLCollection
- 즉 실행결과가 하나인 경우 HTMLLIELement, 복수인 경우 HTMLCollection을 리턴하고 있다. 
- 엘리먼트의 종류에 따라서 리턴되는 객체가 조금씩 다르다
- 엘리먼트 객체에 따라서 프로퍼티가 다르다는 것을 알 수 있다. 하지만 모든 엘리먼트들은 HTMLElement를 상속 받고 있다. 
    > interface HTMLLIElement : HTMLElement {
    > interface HTMLAnchorElement : HTMLElement {

### DOM Tree

모든 엘리먼트는 HTMLElement의 자식이다. 따라서 HTMLElement의 프로퍼티를 똑같이 가지고 있다. 동시에 엘리먼트의 성격에 따라서 자신만의 프로퍼티를 가지고 있는데 이것은 엘리먼트의 성격에 따라서 달라진다. HTMLElement는 Element의 자식이고 Element는 Node의 자식이다. Node는 Object의 자식이다. 이러한 관계를 DOM Tree라고 한다.

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/904/2234.png)

## HTMLCollection

HTMLCollection은 리턴 결과가 복수인 경우에 사용하게 되는 객체다. 유사배열로 배열과 비슷한 사용방법을 가지고 있지만 배열은 아니다. 
HTMLCollection의 목록은 실시간으로 변경된다. 아래 코드를 보자.

```html
<!DOCTYPE html>
<html>
<body>
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li id="active">JavaScript</li>
</ul>
<script>
console.group('before');
var lis = document.getElementsByTagName('li');
for(var i = 0; i < lis.length; i++){
    console.log(lis[i]);
}
console.groupEnd();
console.group('after');
lis[1].parentNode.removeChild(lis[1]);
for(var i = 0; i < lis.length; i++){
    console.log(lis[i]);
}
console.groupEnd();
</script>
</body>
</html>
```

## jQuery 객체

### jQuery 객체란?

jQuery 함수의 리턴값으로 jQuery 함수를 이용해서 선택한 엘리먼트들에 대해서 처리할 작업을 프로퍼티로 가지고 있는 객체다.

### 암시적 반복

jQuery 객체의 가장 중요한 특성은 암시적인 반복을 수행한다는 것이다. DOM과 다르게 jQuery 객체의 메소드를 실행하면 선택된 엘리먼트 전체에 대해서 동시에 작업이 처리된다.

암시적 반복은 값을 설정할 때만 동작한다. 값을 가져올 때는 선택된 엘리먼트 중 첫번째에 대한 값만을 반환한다. 이에 대한 내용은 아래에서 살펴본다.

### 체이닝

chainig이란 선택된 엘리먼트에 대해서 연속적으로 작업을 처리할 수 있는 방법이다. 

### 조회결과

jQuery 객체에는 조회된 엘리먼트가 담겨 있다. jQuery 객체는 일종의 유사배열의 형태로 조회된 엘리먼트를 가지고 있기 때문에 배열처럼 사용해서 엘리먼트를 가져올 수 있다.

```html
<ul>
    <li>html</li>
    <li>css</li>
    <li>JavaScript</li>
</ul>
<script src="http://code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
    console.log($('li').length);
    console.log($('li')[0]);
    var li = $('li');
    for(var i=0; i<li.length; i++){
        console.log(li[i]);
    }
</script>
```

한가지 주의할 것은 li[i]의 값은 해당 엘리먼트에 대한 jQuery 객체가 아니라 DOM 객체라는 것이다. 따라서 jQuery의 기능을 이용해서 이 객체를 제어하려면 jQuery 함수를 이용해야 한다. 

```js
for(var i=0; i<li.length; i++){
    $(li[i]).css('color', 'red');
}
```
> li[i] 는 jQuery객체가 아니라 DOM객체라 .css메소드가 안먹음

```html
<ul>
    <li>html</li>
    <li>css</li>
    <li>JavaScript</li>
</ul>
<script src="http://code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
    var li = $('li');
    li.map(function(index, elem){
        console.log(index, elem);
        $(elem).css('color', 'red');
    })
</script>
```

map은 jQuery 객체의 엘리먼트를 하나씩 순회한다. 이 때 첫번째 인자로 전달된 함수가 호출되는데 첫번째 인자로 엘리먼트의 인덱스, 두번째 인자로 엘리먼트 객체(DOM)이 전달된다.

### jQuery 객체 API

.css와 .attr은 jQuery 객체가 가지고 있는 메소드 중의 하나인데, jQuery는 그 외에도 많은 API를 제공하고 있다. 이에 대한 내용은 jQuery API를 참고하자. https://api.jquery.com

## Element 객체

Element 객체는 엘리먼트를 추상화한 객체다. HTMLElement 객체와의 관계를 이해하기 위해서는 DOM의 취지에 대한 이해가 선행되야 한다. DOM은 HTML만을 제어하기 위한 모델이 아니다. HTML이나 XML, SVG, XUL과 같이 마크업 형태의 언어를 제어하기 위한 규격이기 때문에 Element는 마크업 언어의 일반적인 규격에 대한 속성을 정의하고 있고, 각각의 구체적인 언어(HTML,XML,SVG)를 위한 기능은 HTMLElement, SVGElement, XULElement와 같은 객체를 통해서 추가해서 사용하고 있다.

DOM의 계층구조에서 Element 객체의 위치는 아래와 같다.
![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/904/2240.png)

주요기능
*식별자*
문서내에서 특정한 엘리먼트를 식별하기 위한 용도로 사용되는 API
- Element.classList
- Element.className
- Element.id
- Element.tagName

*조회*
엘리먼트의 하위 엘리먼트를 조회하는 API
- Element.getElementsByClassName
- Element.getElementsByTagName
- Element.querySelector
- Element.querySelectorAll

*속성*
엘리먼트의 속성을 알아내고 변경하는 API
- Element.getAttribute(name)
- Element.setAttribute(name, value)
- Element.hasAttribute(name);
- Element.removeAttribute(name);

### 식별자 API

엘리먼트를 제어하기 위해서는 그 엘리먼트를 조회하기 위한 식별자가 필요하다. 본 수업에서는 식별자 API들에 대해서 알아보자.

HTML에서 엘리먼트의 이름과 id 그리고 class는 식별자로 사용된다. 식별자 API는 이 식별자를 가져오고 변경하는 역할을 한다.

#### Element.tagName

해당 엘리먼트의 태그 이름을 알아낸다. 태그 이름을 변경하지는 못한다.(읽기전용이라는 뜻)

```html
<ul>
    <li>html</li>
    <li>css</li>
    <li id="active" class="important current">JavaScript</li>
</ul>
<script>
console.log(document.getElementById('active').tagName)
</script>
```

#### Element.id

문서에서 id는 단 하나만 등장할 수 있는 식별자다. 아래 예제는 id의 값을 읽고 변경하는 방법을 보여준다. 

```html
<ul>
    <li>html</li>
    <li>css</li>
    <li id="active">JavaScript</li>
</ul>
<script>
var active = document.getElementById('active');
console.log(active.id);
active.id = 'deactive';
console.log(active.id);
</script>
```

#### Element.className

클래스는 여러개의 엘리먼트를 그룹핑할 때 사용한다.
```html
<ul>
    <li>html</li>
    <li>css</li>
    <li id="active">JavaScript</li>
</ul>
<script>
var active = document.getElementById('active');
// class 값을 변경할 때는 프로퍼티의 이름으로 className을 사용한다.
active.className = "important current";
console.log(active.className);
// 클래스를 추가할 때는 아래와 같이 문자열의 더한다.
active.className += " readed"
</script>
```

#### Element.classList

className에 비해서 훨씬 편리한 사용성을 제공한다.
```html
<ul>
    <li>html</li>
    <li>css</li>
    <li id="active" class="important current">JavaScript</li>
</ul>
<script>
function loop(){
    for(var i=0; i<active.classList.length; i++){
        console.log(i, active.classList[i]);
    }
}
// 클래스를 추가
</script>
<input type="button" value="DOMTokenList" onclick="console.log(active.classList);" />
<input type="button" value="조회" onclick="loop();" />
<input type="button" value="추가" onclick="active.classList.add('marked');" />
<input type="button" value="제거" onclick="active.classList.remove('important');" />
<input type="button" value="토글" onclick="active.classList.toggle('current');" />
```

### 조회 API

조회 API는 엘리먼트를 조회하는 기능이다. 조회 방법에 대해서는 이미 여러차례 살펴봤기 때문에 이번 시간에 알아볼 내용은 조회 대상을 제한하는 방법에 대한 것이다. 

지금까지 document.getElementsBy* 메소드를 통해서 엘리먼트를 조회했다. document 객체는 문서 전체를 의미하는 엘리먼트이기 때문에 document의 조회 메소드는 문서 전체를 대상으로 엘리먼트를 조회한다. Element 객체 역시도 getElementsBy* 엘리먼트를 가지고 있는데 Element 객체의 조회 메소드는 해당 엘리먼트의 하위 엘리먼트를 대상으로 조회를 수행한다. 

```html
<ul>
    <li class="marked">html</li>
    <li>css</li>
    <li id="active">JavaScript
        <ul>
            <li>JavaScript Core</li>
            <li class="marked">DOM</li>
            <li class="marked">BOM</li>
        </ul>
    </li>
</ul>
<script>
    var list = document.getElementsByClassName('marked');
    console.group('document');
    for(var i=0; i<list.length; i++){
        console.log(list[i].textContent);
    }
    console.groupEnd();
     
    console.group('active');
    var active = document.getElementById('active');     
    var list = active.getElementsByClassName('marked');
    for(var i=0; i<list.length; i++){
        console.log(list[i].textContent);
    }
    console.groupEnd();
</script>
```

### 속성 API

속성을 제어하는 API는 아래와 같다. 각각의 기능은 이름을 통해서 충분히 유추할 수 있을 것이다.
- Element.getAttribute(name)
- Element.setAttribute(name, value)
- Element.hasAttribute(name);
- Element.removeAttribute(name);

```html
<a id="target" href="http://opentutorials.org">opentutorials</a>
<script>
var t = document.getElementById('target');
console.log(t.getAttribute('href')); //http://opentutorials.org
t.setAttribute('title', 'opentutorials.org'); // title 속성의 값을 설정한다.
console.log(t.hasAttribute('title')); // true, title 속성의 존재여부를 확인한다.
t.removeAttribute('title'); // title 속성을 제거한다.
console.log(t.hasAttribute('title')); // false, title 속성의 존재여부를 확인한다.
</script>
```

#### 속성과 프로퍼티

모든 엘리먼트의 (HTML)속성은 (JavaScript 객체의) 속성과 프로퍼티로 제어가 가능하다. 예제를 보자

```html
<p id="target">
    Hello world
</p>
<script>
    var target = document.getElementById('target');
    // attribute 방식
    target.setAttribute('class', 'important');
    // property 방식
    target.className = 'important';
</script>
```

setAttribute('class', 'important')와 className = 'important'는 같은 결과를 만든다. 하지만 전자는 attribute 방식(속성이라고 부르겠다)이고 후자는 property 방식이다. property 방식은 좀 더 간편하고 속도도 빠르지만 실제 html 속성의 이름과 다른 이름을 갖는 경우가 있다. 그것은 자바스크립트의 이름 규칙 때문이다.

|||
|-|-|
|class|className|
|readonly|readOnly|
|rowspan|rowSpan|
|colspan|colSpan|
|usemap|userMap|
|frameborder|frameBorder|
|for|htmlFor|
|maxlength|maxLength|

### jQuery 속성 제어 API

#### 속성제어

jQuery 객체의 메소드 중 setAttribute, getAttribute에 대응되는 메소드는 attr이다. 또한 removeAttribute에 대응되는 메소드로는 removeAttr이 있다. 

```html
<a id="target" href="http://opentutorials.org">opentutorials</a>
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
var t = $('#target');
console.log(t.attr('href')); //http://opentutorials.org
t.attr('title', 'opentutorials.org'); // title 속성의 값을 설정한다.
t.removeAttr('title'); // title 속성을 제거한다.
</script>
```

#### attribute와 property

DOM과 마찬가지로 jQuery도 속성(attribute)과 프로퍼티를 구분한다. 속성은 attr, 프로퍼티는 prop 메소드를 사용한다.

```html
<a id="t1" href="./demo.html">opentutorials</a>
<input id="t2" type="checkbox" checked="checked" />
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
// 현재 문서의 URL이 아래와 같다고 했을 때
// http://localhost/jQuery_attribute_api/demo2.html
var t1 = $('#t1');
console.log(t1.attr('href')); // ./demo.html 
console.log(t1.prop('href')); // http://localhost/jQuery_attribute_api/demo.html 
 
var t2 = $('#t2');
console.log(t2.attr('checked')); // checked
console.log(t2.prop('checked')); // true
</script>
```

jQuery를 이용하면 프로퍼티의 이름으로 어떤 것을 사용하건 올바른 것으로 교정해준다. 이런 것이 라이브러리를 사용하는 의의라고 할수 있겠다.

```html
<div id="t1">opentutorials</div>
<div id="t2">opentutorials</div>
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
$('#t1').prop('className', 'important'); 
$('#t2').prop('class', 'current');  
</script>
```

### jQuery 조회 범위 제한

#### selector context

가장 간편한 방법은 조회할 때 조회 범위를 제한하는 것이다. 그 제한된 범위를 jQuery에서는 selector context라고 한다.

```html
<ul>
    <li class="marked">html</li>
    <li>css</li>
    <li id="active">JavaScript
        <ul>
            <li>JavaScript Core</li>
            <li class="marked">DOM</li>
            <li class="marked">BOM</li>
        </ul>
    </li>
</ul>
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
    $( ".marked", "#active").css( "background-color", "red" );
    // $( "#active .marked").css( "background-color", "red" );
</script>
```

#### .find()

find는 jQuery 객체 내에서 엘리먼트를 조회하는 기능을 제공한다. 아래의 코드는 위의 예제와 효과가 같다.

```js
$( "#active").find('.marked').css( "background-color", "red" );
$('#active').css('color','blue').find('.marked').css( "background-color", "red" );
```

> **find를 너무 복잡하게 사용하면 코드를 유지보수하기 어렵게 된다.**

## Node 객체
### Node 관계 API
### 노드 종류 API
### 노드 변경 API
### jQuery 노드 변경 API
### 문자열로 노드 제어
# Document 객체
# Text 객체
## 값 API
## 조작 API
# 문서의 기하학적 특성
# 이벤트
## 등록방법
### inline
### 프로퍼티 리스너
### addEventListener()
## 이벤트 전파(버블링과 캡처링)
## 기본동작의 취소
## 이벤트 타입
### 폼
### 문서 로딩
### 마우스
## jQuery 이벤트
### on API 사용법
# 네트워크 통신
## Ajax
## JSON
## jQuery Ajax
# 활용
## Youtube 재생시간 구하기
## Word Counter

