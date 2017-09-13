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
## Navigator 객체
## 창 제어
# DOM
## 제어 대상을 찾기
## jQuery
## 제어 대상을 찾기 (jQuery)
## HTMLElement
## HTMLCollection
## jQuery 객체
## Element 객체
### 식별자 API
### 조회 API
### 속성 API
### jQuery 속성 제어 API
### jQuery 조회 범위 제한
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