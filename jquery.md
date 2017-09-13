# jQuery란?

jQuery는 자바스크립트의 생산성을 향상시켜주는 자바스크립트 라이브러리 입니다. 

라이브러리란 자주 사용되는 로직들을 재활용,유통 가능하도록 만든 로직들의 묶음을 의미합니다. 
자바스크립트의 세계에는 많은 라이브러리들이 있습니다. 
prototype, jQuery, YUI 등등
구글트랜드로 검색을 해보니 현재는 jQuery가 가장 많은 사용자를 가지고 있는 것 같습니다.
jQuery를 이용하면 순수한 자바스크립트로 코딩하는 것 보다 10배 이상 생산성을 높일 수 있습니다. 

또 jQuery는 파생된 라이브러리들을 가지고 있는데요. 
jQuery UI는 jQuery기반의 GUI 라이브러리입니다.
이것을 이용해서 윈도우 에플리케이션과 같은 기능성의 UI를 만들 수 있습니다.

최근에는 jQuery Mobile라는 이름의 모바일 라이브러리를 출시해서 
모바일용 웹에플리케이션을 만드는데도 많은 도움을 주고 있습니다.  

## 라이브러리란?(library)

자주 사용하는 코드들을 재사용할 수 있는 형태로 가공해서 프로그래밍 효율을 높여주는 코드들


## jQuery란?

1. 엘리먼트를 선택하는 강력한 방법과
1. 선택된 엘리먼트들을 효율적으로 제어할 수 있는 다양한 수단을 제공하는
1. 자바스크립트 라이브러리

## Hello world - 첫번째 jQuery

사용방법

1. 직접 서비스 하는 경우
    1. http://jquery.org 에서 jquery 소스코드를 다운로드 한다.
    1. 위의 파일을 서버에 업로드 한 후 웹페이지 안에서 자바스크립트를 삽입한다.
 
1. 구글의 자바스크립트 라이브러리를 사용하는 경우
    1. http://code.google.com/intl/ko-KR/apis/libraries/devguide.html#jquery

```html
<html>
     <body>
         <div class="welcome"></div>
         <div class="welcome"></div>
         <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js"></script>
         <script type="text/javascript">
                 $('.welcome').html('hello world! coding everybody!').css('background-color','yellow');
         </script>
     </body>
 </html>
 ```

## jQuery의 문법

|$(제어대상)|.method1().method2();|
|--|--|
|주어|서술어|

- $대신 jQuery 적어도 됨

# javascript VS jQuery

예제. 탭을 클릭했을 때 포커스를 변경하는 예제

## JavaScript
```html
<html>
    <head>
        <script type="text/javascript">
            function addEvent(target, eventType,eventHandler, useCapture) {
                if (target.addEventListener) { // W3C DOM
                    target.addEventListener(eventType,eventHandler,useCapture?useCapture:false);
                } else if (target.attachEvent) {  // IE DOM
                    var r = target.attachEvent("on"+eventType, eventHandler);
                }
            }
 
     
            function clickHandler(event) {
                var nav = document.getElementById('navigation');
                for(var i = 0; i < nav.childNodes.length; i++) {
                    var child = nav.childNodes[i];
                    if(child.nodeType==3)
                        continue;
                    child.className = '';
                }
                event.target.className = 'selected';
            }
  
            addEvent(window, 'load', function(eventObj) {
                var nav = document.getElementById('navigation');
                for(var i = 0; i < nav.childNodes.length; i++) {
                    var child = nav.childNodes[i];
                    if(child.nodeType==3)
                        continue;
                    addEvent(child, 'click', clickHandler);
                }
            })
        </script>
        <style type="text/css">
            #navigation li {
                list-style:none;
                float:left;
                padding:5px;
            }
            #navigation {
                cursor:pointer;
            }
            #navigation .selected {
                background-color:red;
                color:white;
            }
        </style>
    </head>
    <body>
        <ul id="navigation">
            <li>HTML</li>
            <li>CSS</li>
            <li>javascript</li>
            <li class="selected">jQuery</li>
            <li>PHP</li>
            <li>mysql</li>
        </ul>
    </body>
</html>
```

## jQuery

```html
<html>
    <head>
        <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js"></script>
        <script type="text/javascript">
            $('#navigation li').live('click', function() {
                $('#navigation li').removeClass('selected');
                $(this).addClass('selected');
            })
        </script>
        <style type="text/css">
            #navigation li {
                list-style:none;
                float:left;
                padding:5px;
            }
            #navigation {
                cursor:pointer;
            }
            #navigation .selected {
                background-color:red;
                color:white;
            }
        </style>
    </head>
    <body>
        <ul id="navigation">
            <li>HTML</li>
            <li>CSS</li>
            <li>javascript</li>
            <li class="selected">jQuery</li>
            <li>PHP</li>
            <li>mysql</li>
        </ul>
    </body>
</html>
```

# wrapper
# 선택자
# chain
# event
# 엘리먼트 제어
# 폼
# 탐색
# 에니메이션
# ajax