# 언어소개

- javascript : 웹브라우저를 프로그래밍적으로 제어하기 위한 언어
- 탈웹화되면서 웹서버(node.js)나 그 외에 많은 분야(google apps script, unity 등등)에서 쓰이는 중요한 언어 중 하나로 자리매김하고 있음

# 자바스크립트 기본
## 실행방법과 실습환경
## 숫자와 문자

- javascript의 데이터형식에는 크게 숫자와 문자가 있다.

### 숫자

- 숫자는 또 크게 정수와 실수로 나뉘고 숫자끼리는 사칙연산이 가능하다(+,*,/,-)
- 사칙연산 뿐 아니라 Math같은 함수를 쓰면 제곱, 제곱근, 난수 등 복잡한 계산도 가능하다.

### 문자

- 문자는 ""나 ''사이에 기록되어야 한다.
- 간혹 ''사이에 '를 써야 하는 경우 \' 이와 같은 모습으로 기록을 해주어야 컴퓨터가 문자로서 '를 인지한다.
- \를 이스케이프라 한다.

#### 여러줄의 표시

- 문자를 여러줄 쓰고 싶으면 \n이라고 쓰면 된다.(Enter와 같은 역할)

#### 문자연산

- 숫자도 ""나 ''사이에 기록되면 문자로 인식된다.
- 문자들을 결합하면 결합한 문자들이 이어서 나온다.
- 문자에서도 .length나 .indexof같은 명령을 쓰면 여러 가지 복잡한 기능을 수행할 수 있다.

## 변수

- 변수 : 값을 담는 그릇(값을 유지할 필요가 있을 때)

### 변수의 선언

- var로 시작해서 변수 선언.
- 다른 값을 담을 수도 있다. 그럴 때는 다시 var 쓸 필요 없다.
- 변수에는 숫자, 문자 등등 어떤 것도 담길 수 있다.
- 그것들을 사용해서 연산, 결합 등 할 수 있다
- 변수 2개를 동시에 선언할 때는 var a = 1, b = 2의 형태로 var는 한 번만 쓰고 ,로 연결하면 된다.

### 변수가 없다면

- 변수는 코드의 재활용성을 높이기 위해서 쓴다. 이것은 코딩을 할 때 대단히 중요한 특성이다.

## 주석

- 주석처리 된 코드는 브라우저가 그 코드를 무시해버린다.
- //(한 줄)와 /* ~ */(여러 줄)의 형태가 있다.
- 코드에 대한 설명이 필요할 때 주석을 쓰기도 하고
- 일시적으로 어떤 코드의 동작을 멈출 때 주석을 쓰기도 한다.

## 줄바꿈과 여백

- 줄바꿈: 명령이 끝났다는 뜻
- ;(세미콜론): 줄바꿈의 의미

## 비교

- 참조: http://dorey.github.io/JavaScript-Equality-Table/

### 비교 연산자

- 비교 연산자 : 좌항, 우항을 비교할 때 쓰는 연산자
- 대입 연산자(=) : 우항의 값을 좌항에 대입할 때 사용
- 동등 연산자(==) : 좌항, 우항의 값이 같으면 true, 다르면 false(실질적인 정보의 값을 비교)
- 일치 연산자(===) : 위와 내용은 같음(데이터 형식까지 엄격하게 비교, 동등보다는 이것을 쓰는 것을 권장)
- 부정 연산자(!=): '!'는 부정을 의미한다. '같다'의 부정은 '같지 않다'이다. 이것을 기호로는 '!='로 표시한다. !=의 결과는 ==와 정반대의 결과를 보여준다.
- !==: '!=='는 '!='와 '=='의 관계와 같다. 정확하게 같지 않다는 의미다. 예제는 생략한다.
- >, >=
- undefined : 의도하지 않은 값 없는 상태, null : 의도한 값 없는 상태

## 조건문

- 조건문은 조건에 따라 실행을 달리 하게 하는 것이다.

### Boolean
### 조건문의 문법
#### if
#### else
#### else if

- if(true) {...} 실행한다. if(false) {...} 실행 안한다.
- if(true) {...} else {~~~} true이면 ... 실행하고 false이면 ~~~실행한다.
- else if로 조건문을 더 풍성하게 할 수 있다. 수많은 else if 중 true인것만 실행하고 없다면 else 실행한다. (else는 생략 가능하다)

### 변수와 비교연산자
### 조건문의 중첩
### 논리연산자
#### &&
#### ||
#### !

- &&(AND) : 좌항, 우항 모두 true일 때 전체가 true
- ||(OR) : 좌항, 우항 중 하나만 true이면 전체가 true
- !(NOT) : true이면 false로, false이면 true로 변환
- 
### Boolean의 대체재
#### 01
#### 기타 fase로 간주되는 데이터 형
- '', undefined, 값이 할당되지 않은 변수, null, NaN

## 반복문

- 반복문 : 코드를 반복적으로 실행하게 하는 기술.
- while과 for문이 있다.

### 반복문의 문법
#### while

- while(반복조건) {실행코드} 이런 문법적 형태를 띄는데 무한루프에 빠지지 않도록 하는 초기화변수와 변수를 증가시키는 코드, 반복조건 코드가 필요하다.
- 이것을 한눈에 보기 좋게 표현한 것이 for문이다.

#### for

- for(var i=0; i<10; i++) {실행코드}의 형태를 띈다. 반복문은 반복문끼리 그리고 조건문과도 중첩이 가능하다.
-  i++과 ++i의 차이 : i++은 i를 실행하고 i에 1을 더하고 ++i는 1을 더하고 i를 실행한다.

### 반복문이 없다면
### 반복문의 제어
#### break
#### continue
### 반복문의 중첩

## 함수

- 함수 : 코드의 재사용성을 높이기 위한 기술.

### 함수의 형식
### 함수의 정의와 호출
### 입력과 출력
### 인자
#### 인자란?
#### 복수의 인자

```js
    function function_name(arg){
        code
    }

    // 함수를 정의하는 다른 방법
    var function_name = function(arg){
        code
    }    
```

- 실행할때는 이름(인자)를 하면 실행코드에서 return값이 출력된다.
- 반복문과 같이 반복할 수 있다는 특성이 있지만 반복문은 단순반복이고 함수는 입력값에 따라 출력값이 다르게 반복되고 여러군데에서 사용할 수 있다.
- 코드의 재사용성을 높일 수 있고 유지보수가 용이해지며 가독성 또한 좋아진다.

### 함수를 정의하는 다른 방법

- 이런식의 형태는 익명함수로 함수를 정의하고 바로 호출해야할 때 사용한다. 
```js
var numbering = function (){
    i = 0;
    while(i < 10){
        document.write(i);
        i += 1;
    }   
}
numbering();
```

## 배열
### 배열의 생성
### 배열이 없다면
### 배열의 사용
### 배열의 제어
#### 배열의 크기
#### 배열의 조작
##### 추가
##### 제거
##### 정렬

- 배열 : 여러개의 데이터를 담기 위한 그릇의 역할
- 하나하나의 데이터를 원소라 하고 그것을 식별하는 식별자를 주로 인덱스라 칭한다.(0부터 순서대로 자동매김)
- 배열.length : 배열의 크기 출력
- .push : 배열 끝에 원소 추가
- .pop : 맨 뒤 원소 제거
- .concat : 여러개 원소 추가
- .unshift : 배열 처음에 원소 추가
- .shift : 첫 번째 원소 제거
- .splice : 중간에 추가
    - `array.splice(index, howmany, element1, ..., elementN);`
- .sort : 정렬(사용자가 정의한 기준으로도 정렬 가능)
- .reverse : 역순정렬

## 객체

- 객체: 연관된 데이터를 담는 그릇. 인덱스를 문자로 사용하는 것이 배열과 다른 점.

### 객체의 생성

- var name = {'key값' : value값 , ~~~~}의 형태, 빈 객체 만들고 후에 값 지정도 가능
- 객체와 반복문이 만날 때 
    for(key in 객체){
        ...key - key값 or 객체[key] - value값
    }
- 반복문에서도 위와 같은 방식 사용 가능 
- 객체 안에 객체 또는 함수가 들어갈 수 있음(연관된 데이터, 처리를 그룹핑해서 프로그래밍하는 것을 객체지향프로그래밍이라 함)
- 함수 안에서 this를 사용하면 함수를 가지고 있는 객체를 가리키는 변수로 사용된다.

## 모듈
### 모듈이란
### 모듈이 없다면
### 모듈의 사용
### Node.js에서 모듈의 로드
### 라이브러리

- 모듈: 로직들을 부품화한 것. 부품화하는 과정을 모듈화라 함.
- 모듈화하면 유지보수, 재사용성, 비용절약 등 많은 측면에서 이익이 생김.
- 호스트 환경(웹브라우저,node.js,구글앱스스크립트 등)마다 모듈화하는 방식이 다름(자바스크립트 내부에서 모듈화하는 기능은 없음)
- 웹에서는 `<head>`태그에 자바스크립트파일을 로드하는 방식을 사용
- 라이브러리도 모듈과 비슷한 느낌이지만 모듈은 부품 하나라면 라이브러리는 자주 사용되는 로직을 재사용하기 편리하도록 잘 정리한 일련의 코드들의 집합을 의미한다고 할 수 있다.
- 호스트 환경이란?
> 호스트 환경이란 자바스크립트가 구동되는 환경을 의미한다. 자바스크립트는 브라우저를 위한 언어로 시작했지만, 더 이상 브라우저만을 위한 언어가 아니다. 예를들어 node.js는 서버 측에서 실행되는 자바스크립트다. 이 언어는 자바스크립트의 문법을 따르지만 이 언어가 구동되는 환경은 브라우저가 아니라 서버측 환경이다. 또 구글의 제품 위에서 돌아가는 Google Apps Script 역시 자바스크립트이지만 google apps script가 동작하는 환경은 구글 스프레드쉬트와 같은 구글의 제품 위이다. 여러분은 자바스크립트의 문법을 이용해서 PHP와 같은 서버 시스템을 제어(node.js)하거나 구글의 제품(Google Apps Script)을 제어 할 수 있다. 지금 당장은 어렵겠지만, 언어와 그 언어가 구동되는 환경에 대해서 구분해서 사고 할 수 있어야 한다. 이를 위해서는 다양한 언어를 접해봐야 한다.

## UI와 API 그리고 문서보는 법
### API란?
### 레퍼런스와 튜토리얼
### 자바스크립트의 API
### 자바스크립트 API 문서
### 호스트환경의 API 문서

- Interface : 주체와 주체가 만나는 접점
- UI : User Interface. 사용자와 시스템이 만나는 접점
- API : Application Programming Interface. 시스템과 프로그래머가 만나는 접점(개발자는 시스템, 프로그래밍언어의 API를 통해 프로그램을 제어)
- 프로그래밍을 공부하기 위한 자료 : 튜토리얼(기본적인 조작 안내서(문법)), 레퍼런스(명령어 사전)
- 자바스크립트의 API는 크게 자바스크립트 자체의 API와 자바스크립트가 동작하는 호스트 환경의 API로 구분된다

## 정규표현식
### 정규표현식 생성
- 정규표현식은 두가지 단계로 이루어진다. 하나는 컴파일(compile) 다른 하나는 실행(execution)이다. 우선 컴파일부터 알아보자.

### 컴파일
- 컴파일은 검출하고자 하는 패턴을 만드는 일이다. 우선 정규표현식 객체를 만들어야 한다. 객체를 만드는 방법은 두가지가 있다. a라는 텍스트를 찾아내는 정규표현식을 만들어보자.

#### 정규표현식 리터럴
- `var pattern = /a/`
#### 정규표현식 객체 생성자
- `var pattern = new RegExp('a');`

### 실행
#### RegExp.exec()

```javascript
console.log(pattern.exec('abcdef')); // ["a"]
//실행결과는 문자열 a를 값으로 하는 배열을 리턴한다.

console.log(pattern.exec('bcdefg')); // null
//인자 'bcdef'에는 a가 없기 때문에 null을 리턴한다.
```

#### RegExp.test()
- test는 인자 안에 패턴에 해당되는 문자열이 있으면 true, 없으면 false를 리턴한다.

```javascript
console.log(pattern.test('abcdef')); // true

console.log(pattern.test('bcdefg')); // false
```

### 문자열 메소드 실행
#### String.match()
- RegExp.exec()와 비슷하다.
```javascript
console.log('abcdef'.match(pattern)); // ["a"]
console.log('bcdefg'.match(pattern)); // null
```

#### String.replace()
- 문자열에서 패턴을 검색해서 이를 변경한 후에 변경된 값을 리턴한다.var
```javascript
console.log('abcdef'.replace(pattern, 'A'));  // Abcdef
```

###옵션
- i: i를 붙이면 대소문자를 구분하지 않는다.
- g: g를 붙이면 검색된 모든 결과를 리턴한다.

```javascript
var xi = /a/;
console.log("Abcde".match(xi)); // null
var oi = /a/i;
console.log("Abcde".match(oi)); // ["A"];

var xg = /a/;
console.log("abcdea".match(xg));
var og = /a/g;
console.log("abcdea".match(og));
```

### 사례
#### 캡처
- 괄호안의 패턴은 마치 변수처럼 재사용할 수 있다. 이 때 기호 $를 사용하는데 아래 코드는 coding과 everybody의 순서를 역전시킨다.
```javascript
var pattern = /(\w+)\s(\w+)/;
var str = "coding everybody";
var result = str.replace(pattern, "$2, $1");
console.log(result);
```

#### 치환
- 아래 코드는 본문 중의 URL을 링크 html 태그로 교체한다. 
```javascript
var urlPattern = /\b(?:https?):\/\/[a-z0-9-+&@#\/%?=~_|!:,.;]*/gim;
var content = '생활코딩 : http://opentutorials.org/course/1 입니다. 네이버 : http://naver.com 입니다. ';
var result = content.replace(urlPattern, function(url){
    return '<a href="'+url+'">'+url+'</a>';
});
console.log(result);
```

# 함수지향

함수지향 카테고리의 하위 수업들은 함수형 언어로서 자바스크립트의 면모를 다룬다. 자바스크립트의 핵심적인 도구는 함수다. 자바스크립트의 함수는 매우 강력하다. 함수에 대한 이해 없이는 자바스크립트를 잘 다루기 어렵다. 또한 자바스크립트에서 함수는 객체를 이해하는 데 가장 중요한 기초를 이룬다. 

## 유효범위

- 함수 밖에서 변수를 선언하면 그 변수는 전역변수가 된다. 전역변수는 에플리케이션 전역에서 접근이 가능한 변수다. 다시 말해서 어떤 함수 안에서도 그 변수에 접근 할 수 있다. 
- 지역변수의 유효범위는 함수 안이고, 전역변수의 유효범위는 에플리케이션 전역인데, 같은 이름의 지역변수와 전역변수가 동시에 정의되어 있다면 지역변수가 우선한다.
- 함수 밖에서 var를 쓰면 전역변수, 함수 안에서 var를 쓰면 지역변수
- 전역변수는 거의 쓰이지 않음(프로그램이 커질수록 변수의 이름이 서로 헷갈릴 수 있기 때문. 이런 개념도 그러한 문제때문에 고안된 것)
- *변수를 선언할 때는 꼭 var을 붙이는 것을 습관화해야 한다. 전역변수를 사용해야 하는 경우라면 그것을 사용하는 이유를 명확히 알고 있을 때 사용하도록 하자.*

### 유효범위의 효용

아래 두개의 예제는 변수 i를 지역변수로 사용했을 때와 전역변수로 사용했을 때의 차이점을 보여준다. 전역변수는 각기 다른 로직에서 사용하는 같은 이름의 변수값을 변경시켜서 의도하지 않은 문제를 발생시킨다.

#### 지역변수의 사용

```js
function a (){
    var i = 0;
}
for(var i = 0; i < 5; i++){
    a();
    document.write(i);
}
```

#### 전역변수의 사용

- 본 예제는 무한반복을 발생시킨다. 
```js

function a (){
    i = 0;
}
for(i = 0; i < 5; i++){
    a();
    document.write(i);
}
```

### 전역변수의 사용

- 불가피하게 전역변수를 사용해야 하는 경우는 하나의 객체를 전역변수로 만들고 객체의 속성으로 변수를 관리하는 방법을 사용한다.
```js
MYAPP = {}
MYAPP.calculator = {
    'left' : null,
    'right' : null
}
MYAPP.coordinate = {
    'left' : null,
    'right' : null
}
 
MYAPP.calculator.left = 10;
MYAPP.calculator.right = 20;
function sum(){
    return MYAPP.calculator.left + MYAPP.calculator.right;
}
document.write(sum());
```
- 전역변수를 사용하고 싶지 않다면 아래와 같이 익명함수를 호출함으로서 이러한 목적을 달성할 수 있다
```js
(function(){
    var MYAPP = {}
    MYAPP.calculator = {
        'left' : null,
        'right' : null
    }
    MYAPP.coordinate = {
        'left' : null,
        'right' : null
    }
    MYAPP.calculator.left = 10;
    MYAPP.calculator.right = 20;
    function sum(){
        return MYAPP.calculator.left + MYAPP.calculator.right;
    }
    document.write(sum());
}())
```
- 위와 같은 방법은 자바스크립트에서 로직을 모듈화하는 일반적인 방법이다. 

### 유효범위의 대상 (함수)

- *자바스크립트의 지역변수는 함수에서만 유효하다.*
- 많은 언어들이 블록(대체로 {,})에 대한 유효범위를 제공하는 것과 다른 점이다.

### 정적 유효범위

- 자바스크립트는 함수가 선언된 시점에서의 유효범위를 갖는다. 이러한 유효범위의 방식을 정적 유효범위(static scoping), 혹은 렉시컬(lexical scoping)이라고 한다. 

## 값으로서의 함수와 콜백
### 값으로서의 함수

- 자바스크립트에서 함수는 값으로도 쓰일 수 있다
    - 변수에 담기
        ```js
        var test = function a(){console.log(1)}
        ```
    - 객체 안에 저장하기
        ```js
        a = {
            b:function(){
            }
        };
        ```
    - 다른 함수의 인자로 사용하기
        ```js
        function cal(func, num){
            return func(num)
        }
        function increase(num){
            return num+1
        }
        function decrease(num){
            return num-1
        }
        alert(cal(increase, 1));
        alert(cal(decrease, 1));
        ```
    - 다른 함수의 리턴값으로 사용하기, 
        ```js
        function cal(mode){
            var funcs = {
                'plus' : function(left, right){return left + right},
                'minus' : function(left, right){return left - right}
            }
            return funcs[mode];
        }
        alert(cal('plus')(2,1));
        alert(cal('minus')(2,1));   
        ```
    - 배열의 값으로 사용하기 등
        ```js
        var process = [
            function(input){ return input + 10;},
            function(input){ return input * input;},
            function(input){ return input / 2;}
            ];
        var input = 1;
        for(var i = 0; i < process.length; i++){
            input = process[i](input);
        }
        alert(input);   
        ```
> 객체 안에서 key는 변수 역할, 속성이라고도 부르고 value에 함수가 담긴다면 이는 메소드라 부른다

### 콜백
#### 처리의 위임
값으로 사용될 수 있는 특성을 이용하면 함수의 인자로 함수로 전달할 수 있다. 값으로 전달된 함수는 호출될 수 있기 때문에 이를 이용하면 함수의 동작을 완전히 바꿀 수 있다. 인자로 전달된 함수 sortNumber의 구현에 따라서 sort의 동작방법이 완전히 바뀌게 된다.

```js
function sortNumber(a,b){
    // 위의 예제와 비교해서 a와 b의 순서를 바꾸면 정렬순서가 반대가 된다.
    return b-a;
}
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array, [20,10,9,8,7,6,5,4,3,2,1]
```
- 여기서 *sortNumber*가 callback이다.

#### 비동기 처리

콜백은 비동기처리에서도 유용하게 사용된다. 시간이 오래걸리는 작업이 있을 때 이 작업이 완료된 후에 처리해야 할 일을 콜백으로 지정하면 해당 작업이 끝났을 때 미리 등록한 작업을 실행하도록 할 수 있다. 대표적으로 Ajax라는 기법이있음.(강의 영상 참조))

  
## 클로저

- 클로저(closure)는 내부함수가 외부함수의 맥락(context)에 접근할 수 있는 것을 가르킨다. 클로저는 자바스크립트를 이용한 고난이도의 테크닉을 구사하는데 필수적인 개념으로 활용된다.  
- 내부함수 : 함수 안에 함수가 선언되 있는 것
- 외부함수 : 내부함수 바깥에 선언된 함수
- 내부함수는 외부함수의 지역변수에 접근할 수 있다.
- 클로저(closure)는 내부함수와 밀접한 관계를 가지고 있는 주제다.
- 외부함수가 소멸되도 내부함수는 외부함수의 지역변수에 접근할수 있다.
- 클로저란 내부함수가 외부함수의 지역변수에 접근 할 수 있고, 외부함수는 외부함수의 지역변수를 사용하는 내부함수가 소멸될 때까지 소멸되지 않는 특성을 의미한다.
- 프라이빗변수 : 정보를 아무나 수정하는 것을 방지하는 기법(이 기법에 클로저를 사용)
> Private 속성은 객체의 외부에서는 접근 할 수 없는 외부에 감춰진 속성이나 메소드를 의미한다. 이를 통해서 객체의 내부에서만 사용해야 하는 값이 노출됨으로서 생길 수 있는 오류를 줄일 수 있다. 자바와 같은 언어에서는 이러한 특성을 언어 문법 차원에서 지원하고 있다.

```js
function factory_movie(title){
    return {
        get_title : function (){
            return title;
        },
        set_title : function(_title){
            title = _title
        }
    }
}
ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');
 
alert(ghost.get_title());
alert(matrix.get_title());
 
ghost.set_title('공각기동대');
 
alert(ghost.get_title());
alert(matrix.get_title());
```
위의 예제를 통해서 알 수 있는 것들을 정리해보면 아래와 같다.

1. 클로저는 객체의 메소드에서도 사용할 수 있다. 위의 예제는 함수의 리턴값으로 객체를 반환하고 있다. 이 객체는 메소드 get_title과 set_title을 가지고 있다. 이 메소드들은 외부함수인 factory_movie의 인자값으로 전달된 지역변수 title을 사용하고 있다.

2. 동일한 외부함수 안에서 만들어진 내부함수나 메소드는 외부함수의 지역변수를 공유한다. 17행에서 실행된 set_title은 외부함수 factory_movie의 지역변수 title의 값을 '공각기동대'로 변경했다. 19행에서 ghost.get_title();의 값이 '공각기동대'인 것은 set_title와 get_title 함수가 title의 값을 공유하고 있다는 의미다.

3. 그런데 똑같은 외부함수 factory_movie를 공유하고 있는 ghost와 matrix의 get_title의 결과는 서로 각각 다르다. 그것은 외부함수가 실행될 때마다 새로운 지역변수를 포함하는 클로저가 생성되기 때문에 ghost와 matrix는 서로 완전히 독립된 객체가 된다.

4. factory_movie의 지역변수 title은 2행에서 정의된 객체의 메소드에서만 접근 할 수 있는 값이다. 이 말은 title의 값을 읽고 수정 할 수 있는 것은 factory_movie 메소드를 통해서 만들어진 객체 뿐이라는 의미다. JavaScript는 기본적으로 Private한 속성을 지원하지 않는데, 클로저의 이러한 특성을 이용해서 Private한 속성을 사용할 수 있게된다.

## arguments

- argument : 인자의 정보를 담고 있는 *객체?*
- *arguments는 사실 배열은 아니다. 실제로는 arguments 객체의 인스턴스다.*
- 자바스크립트에서는 매개변수를 정의하지 않은 상태에서 인자의 값을 줘도 에러가 나지 않는다
- 함수의 정의부분에서 인자에 대한 구현이 없음에도 인자를 전달 할 수 있는 것은 왜 그럴까? 그것은 arguments라는 특수한 배열이 있기 때문이다.
- arguments는 함수안에서 사용할 수 있도록 그 이름이나 특성이 약속되어 있는 일종의 배열이다. 
- argument안에 인자의 정보를 가진 객체가 담기게 된다.
```js
function sum(){
    var i, _sum = 0;    
    for(i = 0; i < arguments.length; i++){
        document.write(i+' : '+arguments[i]+'<br />');
        _sum += arguments[i];
    }   
    return _sum;
}
document.write('result : ' + sum(1,2,3,4));
```

### 매개변수의 수

- argument.length를 하게 되면 사용자가 입력한 인자의 수가 리턴되지만, 함수.length하게 되면 매개변수를 몇 개나 정의했는지가 리턴된다.
```js
function zero(){
    console.log(
        'zero.length', zero.length,
        'arguments', arguments.length
    );
}
function one(arg1){
    console.log(
        'one.length', one.length,
        'arguments', arguments.length
    );
}
function two(arg1, arg2){
    console.log(
        'two.length', two.length,
        'arguments', arguments.length
    );
}
zero(); // zero.length 0 arguments 0 
one('val1', 'val2');  // one.length 1 arguments 2 
two('val1');  // two.length 2 arguments 1
```

## 함수의 호출

- JavaScript는 함수를 호출하는 특별한 방법을 제공한다.
- JavaScript에선 함수 역시 객체이다.
- JavaScript에선 함수는 Function이라는 객체의 인스턴스다.
- 따라서 함수는 객체 Function이 가지고 있는 메소드들을 상속하고 있다. - 지금 이야기하려는 메소드는 `Function.apply`과 `Function.call`이다.
- 이 메소드들을 이용해서 함수를 호출해보자.

```js
o1 = {val1:1, val2:2, val3:3}
o2 = {v1:10, v2:50, v3:100, v4:25}
function sum(){
    var _sum = 0;
    for(name in this){
        _sum += this[name];
    }
    return _sum;
}
alert(sum.apply(o1)) // 6
alert(sum.apply(o2)) // 185
```
```js
function sum(){
    var _sum = 0;
    for(name in this){
        if(typeof this[name] !== 'function') //이거 없이 실행하면 함수의 body까지 같이 붙어나와서 그럼. 객체 o1, o2의 값을 열거할 때 함수 sum도 포함되기 때문이다.)
            _sum += this[name];
    }
    return _sum;
}
o1 = {val1:1, val2:2, val3:3, sum:sum}
o2 = {v1:10, v2:50, v3:100, v4:25, sum:sum}

alert(o1.sum()) // 6
alert(o2.sum()) // 185
```
> 이렇게 하면 불편하니까 apply를 사용한다.
*apply를 사용하면 함수가(sum) 객체의(o1, o2) 속성인것처럼 쓸 수 있다.*

- this는 함수가 호출될때 정해진다
- sum.apply(o1) 하면 o1이 this가 된다
- var this = o1; 이런 코드가 들어가는셈
- 저런 코드를 쓰면 o1, o2객체에 sum이라는 메소드가 생기는 셈
- sum.apply(o1)은 함수 sum을 객체 o1의 메소드로 만들고 sum을 호출한 후에 sum을 삭제한다. 아래와 비슷하다. (실행결과가 조금 다를 것이다. 그것은 함수 for in문으로 객체 o1의 값을 열거할 때 함수 sum도 포함되기 때문이다.)
```js
o1.sum = sum;
alert(o1.sum());
delete o1.sum();
```
- sum의 o1 소속의 메소드가 된다는 것은 이렇게 바꿔 말할 수 있다. 함수 sum에서 this의 값이 전역객체가 아니라 o1이 된다는 의미다. 일반적인 객체지향 언어에서는 하나의 객체에 소속된 함수는 그 객체의 소유물이 된다. 하지만 *JavaScript에서 함수는 독립적인 객체로서 존재하고, apply나 call 메소드를 통해서 다른 객체의 소유물인 것처럼 실행할 수 있다.*
- 만약 apply의 첫번째 인자로 null을 전달하면 apply가 실행된 함수 인스턴스는 전역객체(브라우저에서는 window)를 맥락으로 실행되게 된다.

# 객체지향
## 객체지향 프로그래밍

객체지향 프로그래밍(Object-Oriented Programming)은 좀 더 나은 프로그램을 만들기 위한 프로그래밍 패러다임으로 로직을 상태(state)와 행위(behave)로 이루어진 객체로 만드는 것이다. 이 객체들을 마치 레고 블럭처럼 조립해서 하나의 프로그램을 만드는 것이 객체지향 프로그래밍이라고 할 수 있다. 다시 말해서 객체지향 프로그래밍은 객체를 만드는 것이다.

> 객체지향 프로그래밍을 학습하는데 장애 중의 하나는 번역이다. Object를 번역한 객체는 현실에서는 거의 쓰지 않는 말이고, 머랄까 철학적인 느낌을 자아낸다. 그래서 객체지향 프로그래밍을 처음 접하는 입문자들은 객체지향 프로그래밍을 철학적인 탐구의 대상으로 파악하는 경향을 보이는데, 필자의 생각에 이것은 공부를 어렵게 할 뿐 도움이 되지 않는다. 쉽게 생각하자. 객체는 변수와 메소드를 그룹핑한 것이다.

### 문법과 설계

객체지향 프로그래밍 교육은 크게 두 가지로 구분된다.

#### 문법

객체지향을 편하게 할 수 있도록 언어가 제공하는 기능을 익히는 것이다. 이러한 기능들은 if, for문처럼 문법적인 구성을 가지고 있다. 이 문법을 이해하고, 숙지해야 객체를 만들 수 있다. 객체를 만드는 법에 대한 학습이라고 할 수 있다. 

#### 설계

좋은 객체를 만드는 법이다. 이것을 다른 말로는 설계를 잘하는 법이라고 할 수 있다. 좋은 설계는 현실을 잘 반영해야 한다. 복잡함 속에서 필요한 관점만을 추출하는 행위를 추상화라고 한다. 좋은 설계는 문법을 배우는 것보다 훨씬 어려운 일이다. 심지어 이것은 지식을 넘어서 지혜의 영역이다. 스스로 경험하고 깨우쳐서 자기화시켜야 한다.

### 부품화

객체 지향과 부품화를 동일시 할 수는 없지만 부품화라고 하는 소프트웨어의 큰 흐름은 객체 지향이 만들어지는데 지대한 공헌을 했다고 할 수 있다.
문제가 생겼을 때 그 문제가 어디에서 발생한 것인지 파악하고 해결하기가 훨씬 쉬워진다.
기준은 무엇일까? 그 기준을 세우는 것이 추상화일 것이다.

### 은닉화, 캡슐화

그런데 부품화라고 하는 목표는 단순히 동일한 기능을 하는 메소드와 변수를 그룹핑한다고 달성되는 것은 아니다. 제대로된 부품이라면 그것이 어떻게 만들어졌는지 모르는 사람도 그 부품을 사용하는 방법만 알면 쓸 수 있어야 한다. 이를테면 모니터가 어떻게 동작하는지 몰라도 컴퓨터와 모니터를 연결하는 방법만 알면 화면을 표시 할 수 있는 것과 같은 이치다. 즉 내부의 동작 방법을 단단한 케이스 안으로 숨기고 사용자에게는 그 부품의 사용방법만을 노출하고 있는 것이다. 이러한 컨셉을 정보의 은닉화(Information Hiding), 또는 캡슐화(Encapsulation)라고 부른다. 자연스럽게 사용자에게는 그 부품을 사용하는 방법이 중요한 것이 된다.  

### 인터페이스

잘 만들어진 부품이라면 부품과 부품을 서로 교환 할 수 있어야 한다. 예를들어보자. 집에 있는 컴퓨터에 A사의 모니터를 연결하다가 B사의 모니터를 연결 할 수 있다. 또 집에 있던 모니터에 A사의 컴퓨터를 연결해서 사용하다가 새로운 컴퓨터를 구입하면서 B사의 컴퓨터를 연결 할 수 있다. 모니터와 컴퓨터는 서로가 교환관계에 있는 것이다. 이것은 모니터와 컴퓨터를 연결하는 케이블의 규격이 표준화 되어 있기 때문에 가능한 일이다. 아래의 그림을 보자. 모니터와 컴퓨터를 연결하는 케이블인 HDMI를 보여준다.
컴퓨터와 모니터를 만드는 업체들은 위와 같은 케이블의 규격을 공유한다. 모니터 입장에서는 컴퓨터가, 컴퓨터 입장에서는 모니터가 어떤 식으로 만들어졌는지는 신경쓰지 않는다. 각각의 부품은 미리 정해진 약속에 따라서 신호를 입, 출력하고, 연결점의 모양을 표준에 맞게 만들면 된다. 이러한 연결점을 인터페이스(interface)라고 한다. 위의 그림을 보면 HDMI 케이블의 연결점은 특유의 생김새가 있다. 만약 HDMI 케이블을 랜선을 연결하는 구멍에 연결하려고 한다면 어떻게 될까? 동작하지 않을 뿐 아니라 연결 자체가 되지 않는다. 인터페이스란 이질적인 것들이 결합하는 것을 막아주는 역할도 하는 것이다. 즉 인터페이스는 부품들 간의 약속이다. 이러한 약속을 프로그래밍적으로는 어떻게 구현하는가도 살펴본다.

## 생성자와 new
### 객체

객체란 서로 연관된 변수와 함수를 그룹핑한 그릇이라고 할 수 있다. 객체 내의 변수를 프로퍼티(property) 함수를 메소드(method)라고 부른다. 객체를 만들어보자.

```js
var person = {}
person.name = 'egoing';
person.introduce = function(){
    return 'My name is '+this.name;
}
document.write(person.introduce());
```

객체를 만드는 과정에 분산되어 있다. 객체를 정의 할 때 값을 셋팅하도록 코드를 바꿔보자.

```js
var person = {
    'name' : 'egoing',
    'introduce' : function(){
        return 'My name is '+this.name;
    }
}
document.write(person.introduce());
```

만약 다른 사람의 이름을 담을 객체가 필요하다면 객체의 정의를 반복해야 할 것이다. 객체의 구조를 재활용할 수 있는 방법이 필요하다. 이 때 사용하는 것이 생성자다.

### 생성자

- 생성자(constructor)는 객체를 만드는 역할을 하는 함수다.
- 자바스크립트에서 함수는 재사용 가능한 로직의 묶음이 아니라 객체를 만드는 창조자라고 할 수 있다.

```js
function Person(name){
    this.name = name;
    this.introduce = function(){
        return 'My name is '+this.name; 
    }   
}
var p1 = new Person('egoing');
document.write(p1.introduce()+"<br />");
 
var p2 = new Person('leezche');
document.write(p2.introduce());
```
- 생성자 내에서 이 객체의 프로퍼티를 정의하고 있다. 이러한 작업을 초기화라고 한다. 이를 통해서 코드의 재사용성이 대폭 높아졌다.
- 코드를 통해서 알 수 있듯이 생성자 함수는 일반함수와 구분하기 위해서 첫글자를 대문자로 표시한다

### 자바스크립트 생성자의 특징

일반적인 객체지향 언어에서 생성자는 클래스의 소속이다. 하지만 자바스크립트에서 객체를 만드는 주체는 함수다. 함수에 new를 붙이는 것을 통해서 객체를 만들 수 있다는 점은 자바스크립트에서 함수의 위상을 암시하는 단서이면서 또 자바스크립트가 추구하는 자유로움을 보여주는 사례라고 할 수 있다.

## 전역객체
### 전역객체란?

전역객체(Global object)는 특수한 객체다. 모든 객체는 이 전역객체의 프로퍼티다.

```js
function func(){
    alert('Hello?');    
}
func();
window.func();
```

func();와 window.func();는 모두 실행이 된다. *모든 전역변수와 함수는 사실 window 객체의 프로퍼티다. 객체를 명시하지 않으면 암시적으로 window의 프로퍼티로 간주된다.*

```js
var o = {'func':function(){
    alert('Hello?');
}}
o.func();
window.o.func();
```
자바스크립트에서 모든 객체는 기본적으로 전역객체의 프로퍼티임을 알 수 있다. 

*전역객체는 암시적으로 모든 변수, 함수에 쓰이므로 생략이 가능하다.*

> 웹브라우저에서만 window가 정의되어있네. node에선 안됨.

### 전역객체 API

ECMAScript에서는 전역객체의 API를 정의해두었다. 그 외의 API는 호스트 환경에서 필요에 따라서 추가로 정의하고 있다. 이를테면 웹브라우저 자바스크립트에서는 alert()이라는 전역객체의 메소드가 존재하지만 node.js에는 존재하지 않는다. 또한 전역객체의 이름도 호스트환경에 따라서 다른데, 웹브라우저에서 전역객체는 `window`이지만 node.js에서는 `global`이다. 

## this

this는 함수 내에서 함수 호출 맥락(context)를 의미한다. 맥락이라는 것은 상황에 따라서 달라진다는 의미인데 즉 함수를 어떻게 호출하느냐에 따라서 this가 가리키는 대상이 달라진다는 뜻이다. 함수와 객체의 관계가 느슨한 자바스크립트에서 this는 이 둘을 연결시켜주는 실질적인 연결점의 역할을 한다.

### 함수호출

*함수를 호출했을 때 this는 전역객체인 window와 같다.*

```js
function func(){
    if(window === this){
        document.write("window === this");
    }
}
func(); //window === this
```

### 메소드의 호출

*메소드를 호출했을 때 객체의 소속인 메소드의 this는 그 객체를 가르킨다.*
```js
var o = {
    func : function(){
        if(o === this){
            document.write("o === this");
        }
    }
}
o.func();   // o === this
```

### 생성자의 호출

아래 코드는 함수를 호출했을 때와 new를 이용해서 생성자를 호출했을 때의 차이를 보여준다.
```js
var funcThis = null; 
 
function Func(){
    funcThis = this;
}
var o1 = Func();
if(funcThis === window){
    document.write('window <br />');
}
 
var o2 = new Func();
if(funcThis === o2){
    document.write('o2 <br />');
}
```
```js
// 결과
window 
o2
```

생성자는 빈 객체를 만든다. 그리고 이 객체내에서 this는 만들어진 객체를 가르킨다. 이것은 매우 중요한 사실이다. 생성자가 실행되기 전까지는 객체는 변수에도 할당될 수 없기 때문에 this가 아니면 객체에 대한 어떠한 작업을 할 수 없기 때문이다. 

```js
function Func(){
    document.write(o);
}
var o = new Func(); // 이 부분의 생성자가 실행된 것.
// 결과: undefined
```
- 생성자가 먼저 실행되고 o에 할당된다.
- 할당되기 전까진 undefined니까 결과가 undefined로 나옴.

### apply, call

- 함수의 메소드인 apply, call을 이용하면 this의 값을 제어할 수 있다. 
```js
var o = {}
var p = {}
function func(){
    switch(this){
        case o:
            document.write('o<br />');
            break;
        case p:
            document.write('p<br />');
            break;
        case window:
            document.write('window<br />');
            break;          
    }
}
func();           // window
func.apply(o);    // o
func.apply(p);    // p
```

## 상속
### 상속(Inheritance)이란?

객체는 연관된 로직들로 이루어진 작은 프로그램이라고 할 수 있다. 상속은 객체의 로직을 그대로 물려 받는 또 다른 객체를 만들 수 있는 기능을 의미한다. 단순히 물려받는 것이라면 의미가 없을 것이다. 기존의 로직을 수정하고 변경해서 파생된 새로운 객체를 만들 수 있게 해준다. 

- 코드의 중복이 줄어든다.
- 상속법 : 자식객체.prototype = new 부모객체(); / 부모객체에서 프로퍼티들 정의할 때 prototype 붙여줌
- 기능추가 역시 자식객체를 생성하고 prototype을 붙여서 프로퍼티를 정의함.

## prototype

prototype이란 무엇인가? 한국어로는 원형정도로 번역되는 prototype은 말 그대로 객체의 원형이라고 할 수 있다. 함수는 객체다. 그러므로 생성자로 사용될 함수도 객체다. *객체는 프로퍼티를 가질 수 있는데 prototype이라는 프로퍼티는 그 용도가 약속되어 있는 특수한 프로퍼티다.* prototype에 저장된 속성들은 생성자를 통해서 객체가 만들어질 때 그 객체에 연결된다. 

```js
function Ultra(){}
Ultra.prototype.ultraProp = true;
 
function Super(){}
Super.prototype = new Ultra();
 
function Sub(){}
Sub.prototype = new Super();
 
var o = new Sub();
console.log(o.ultraProp);  // true
```

생성자 Sub를 통해서 만들어진 객체 o가 Ultra의 프로퍼티 ultraProp에 접근 가능한 것은 prototype 체인으로 Sub와 Ultra가 연결되어 있기 때문이다. 내부적으로는 아래와 같은 일이 일어난다.

1. 객체 o에서 ultraProp를 찾는다.
1. 없다면 Sub.prototype.ultraProp를 찾는다.
1. 없다면 Super.prototype.ultraProp를 찾는다. 
1. 없다면 Ultra.prototype.ultraProp를 찾는다.
prototype는 객체와 객체를 연결하는 체인의 역할을 하는 것이다. 이러한 관계를 prototype chain이라고 한다.

> Super.prototype = Ultra.prototype 으로하면 안된다. 이렇게하면 Super.prototype의 값을 변경하면 그것이 Ultra.prototype도 변경하기 때문이다. Super.prototype = new Ultra();는 Ultra.prototype의 원형으로 하는 객체가 생성되기 때문에 new Ultra()를 통해서 만들어진 객체에 변화가 생겨도 Ultra.prototype의 객체에는 영향을 주지 않는다.

## 표준 내장 객체의 확장

- 표준 내장 객체(Standard Built-in Object) : 자바스크립트가 기본적으로 제공하는 객체.
- 자바스크립트는 아래와 같은 내장 객체를 가지고 있다. 
    - Object
    - Function
    - Array
    - String
    - Boolean
    - Number
    - Math
    - Date
    - RegExp
- 표준 내장 객체에 우리가 필요로 하는 기능이 없을 수도 있다. 그럴 때 그 함수를 직접 만들 수도 있지만 객체에 메소드로 확장시키는 방법도 있다.
- 객체.prototype.메소드이름 = function() {}하게 되면 그 객체의 prototype에 메소드가 추가되면서 객체를 사용할 때도 메소드를 사용할 수 있게 된다.

### 배열을 확장

배열을 확장해보자. 아래 코드는 배열에서 특정한 값을 랜덤하게 추출하는 코드다. 

```js
var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
function getRandomValueFromArray(haystack){
    var index = Math.floor(haystack.length*Math.random());
    return haystack[index]; 
}
console.log(getRandomValueFromArray(arr));
```

이렇게 작성해도 된다! 잘못한 것이 아니다. 하지만 조금 더 세련된 방법은 이 함수를 배열 객체에 포함시키는 것이다. 그렇게하면 마치 배열에 내장된 메소드인 것처럼 위의 기능을 사용할 수 있다.

```js
Array.prototype.rand = function(){
    var index = Math.floor(this.length*Math.random());
    return this[index];
}
var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
console.log(arr.rand());
```

## Object

- Object 객체는 객체의 가장 기본적인 형태를 가지고 있는 객체이다. 다시 말해서 아무것도 상속받지 않는 순수한 객체다. 자바스크립트에서는 값을 저장하는 기본적인 단위로 Object를 사용한다. 동시에 자바스크립트의 모든 객체는 Object 객체를 상속 받는데, 그런 이유로 모든 객체는 Object 객체의 프로퍼티를 가지고 있다.
- 또한 Object 객체를 확장하면 모든 객체가 접근할 수 있는 API를 만들 수 있다. 아래는 Object 객체를 확장한 사례다.

```js
Object.prototype.contain = function(neddle) {
    for(var name in this){
        if(this[name] === neddle){
            return true;
        }
    }
    return false;
}
var o = {'name':'egoing', 'city':'seoul'}
console.log(o.contain('egoing'));
var a = ['egoing','leezche','grapittie'];
console.log(a.contain('leezche'));
```

- 그런데 Object 객체는 확장하지 않는 것이 바람직하다. 왜냐하면 모든 객체에 영향을 주기 때문이다.
- object가 가진 메소드는 두가지 형태가 있다. Object.메소드이름()과 Object.prototype.메소드이름()인데 첫 번째 형태는 Object 자신만 쓸 수 있고 두 번째 형태는 모든 객체가 쓸 수 있는데 그 이유는 모든 객체가 Object를 상속하기 때문이다.
- 역으로 Object의 prototype을 이용해서 메소드를 만들면 모든 객체가 쓸 수 있는 강력한 메소드를 만들 수 있지만 그만큼 위험해서 의도하지 않은 결과를 초래할 수 있기 때문에 되도록 권장하진 않는다.

## 데이터 타입
### 원시 데이터 타입

데이터 타입이란 데이터의 형태를 의미한다. 데이터 타입은 크게 두가지로 구분할 수 있다. 객체와 객체가 아닌 것. 그럼 객체가 아닌 것은 무엇일까?

- 숫자
- 문자열
- 불리언(true/false)
- null
- undefined

객체가 아닌 데이터 타입을 *원시 데이터 타입(primitive type)*이라고 한다. 그 외의 모든 데이터 타입들은 객체다. 

## 레퍼 객체

```js
var str = 'coding';
console.log(str.length);        // 6
console.log(str.charAt(0));     // "C"
```

문자열은 분명히 프로퍼티와 메소드가 있다. 그렇다면 객체다. 그런데 왜 문자열이 객체가 아니라고 할까? 그것은 내부적으로 문자열이 원시 데이터 타입이고 문자열과 관련된 어떤 작업을 하려고 할 때 자바스크립트는 임시로 문자열 객체를 만들고 사용이 끝나면 제거하기 때문이다. 이러한 처리는 내부적으로 일어난다. 그렇기 때문에 몰라도 된다. 하지만 원시 데이터 타입과 객체는 좀 다른 동작 방법을 가지고 있기 때문에 이들을 분별하는 것은 결국엔 필요하다.

```js
var str = 'coding';
str.prop = 'everybody';
console.log(str.prop);      // undefined
```

str.prop를 하는 순간에 자바스크립트 내부적으로 String 객체가 만들어진다. prop 프로퍼티는 이 객체에 저장되고 이 객체는 곧 제거 된다. 그렇기 때문에 prop라는 속성이 저장된 객체는 존재하지 않게된다. 이러한 특징은 일반적인 객체의 동작 방법과는 다르다. 

하지만 문자열과 관련해서 필요한 기능성을 객체지향적으로 제공해야 하는 필요 또한 있기 때문에 원시 데이터 형을 객체처럼 다룰 수 있도록 하기 위한 객체를 자바스크립트는 제공하고 있는데 그것이 *레퍼객체(wrapper object)*다.

레퍼객체로는 String, Number, Boolean이 있다. null과 undefined는 레퍼 객체가 존재하지 않는다.

## 참조
### 복제

전자화된 시스템의 가장 중요한 특징은 복제다. 현실의 사물과 다르게 전자화된 시스템 위의 데이터를 복제 하는데는 비용이 거의 들지 않는다. 바로 이러한 특징이 소프트웨어를 기존의 산업과 구분하는 가장 큰 특징일 것이다. 프로그래밍에서 복제가 무엇인가를 살펴보자.

```js
var a = 1;
var b = a;
b = 2;
console.log(a); // 1
```

결과는 당연하다. 값을 변경한 것은 변수 b이기 때문에 변수 a에 담겨있는 값은 그대로이다. 변수 b의 값에 변수 a의 값이 복제된 것이다.

### 참조

```js
var a = {'id':1};
var b = a;
b.id = 2;
console.log(a.id);  // 2
```

변수 b에 담긴 객체의 id 값을 2로 변경했을 뿐인데 a.id의 값도 2가 된 것이다. 이것은 변수 b와 변수 a에 담긴 객체가 서로 같다는 것을 의미하다. 참조(reference)의 세계에 온 것을 환영한다.

앞서 필자는 전자화된 세계에서 가장 중요한 특징으로 복제를 들었다. 그런데 복제만으로 전자화된 시스템을 설명하는 것은 조금 부족하다. 비유하자면 복제는 파일을 복사하는 것이고 참조는 심볼릭 링크(symbolic link) 혹은 바로가기(윈도우)를 만드는 것과 비슷하다. 원본 파일에 대해서 심볼릭 링크를 만들면 원본이 수정되면 심볼릭 링크에도 그 내용이 실시간으로 반영되는 것과 같은 효과다. 심볼릭 링크를 통해서 만든 파일은 원본 파일에 대한 주소 값이 담겨 있다. 누군가 심볼릭 링크에 접근하면 컴퓨터는 심볼릭 링크에 저장된 원본의 주소를 참조해서 원본의 위치를 알아내고 원본에 대한 작업을 하게 된다. 다시 말해서 원본을 복제한 것이 아니라 원본 파일을 참조(reference)하고 있는 것이다. 덕분에 저장 장치의 용량을 절약할 수 있고, 원본 파일을 사용하고 있는 모든 복제본이 동일한 내용을 유지할 수 있게 된다. 참조는 전자화된 세계의 극치라고 할 수 있다.

프로그래밍에서 광범위하게 사용하는 라이브러리라는 개념도 일종의 참조라고 할 수 있다. 공용 라이브러리를 사용하게 되면 하나의 라이브러리를 여러 애플리케이션에서 공유해서 사용하게 된다. 라이브러리의 내용이 변경되면 이를 참조하고 있는 애플리케이션에도 내용이 반영되게 된다. 또 우리가 변수를 사용하는 이유도 말하자면 참조를 위해서라고 할 수 있을 것이다. 본질을 파악하면 이해력도 높아지고 암기할 것도 줄어든다.

아래 두 개의 구문의 차이점을 생각해보자.

```js
a = 1;
a = {'id':1};
```

무엇일까? 전자는 데이터형이 숫자이고 후자는 객체다. 숫자는 원시 데이터형(기본 데이터형, Primitive Data Types)이다. 자바스크립트에서는 원시 데이터형을 제외한 모든 데이터 타입은 객체이다. *객체를 다른 말로는 참조 데이터 형(참조 자료형)이라고도 부른다. 기본 데이터형은 위와 같이 복제 되지만 참조 데이터형은 참조된다. 모든 객체는 참조 데이터형이다.*

> *정리하면 변수에 담겨있는 데이터가 원시형이면 그 안에는 실제 데이터가 들어있고, 객체면 변수 안에는 데이터에 대한 참조 방법이 들어있다고 할 수 있다.*

### 함수

그럼 일종의 변수할당이라고 할 수 있는 메소드의 매개변수는 어떻게 동작하는가를 살펴보자. 조금 복잡하므로 꼼꼼하게 살펴봐야 한다. 예제를 보자.

다음은 원시 데이터 타입을 인자로 넘겼을 때의 동작 모습이다.

```js
var a = 1;
function func(b){
    b = 2;
}
func(a);
console.log(a);    // 1
```

다음은 참조 데이터 타입을 인자로 넘겼을 때 동작하는 장면이다. 

```js
var a = {'id':1};
function func(b){
    b = {'id':2};    // 새로운 객체를 만드는것
}
func(a);
console.log(a.id);  // 1
```

함수 func의 파라미터 b로 전달된 값은 객체 a이다. (b = a) *b를 새로운 객체로 대체하는 것은 (b = {'id':2}) b가 가르키는 객체를 변경하는 것이기 때문에 객체 a에 영향을 주지 않는다.*

하지만 아래는 다르다.

```js
var a = {'id':1};
function func(b){
    b.id = 2;       // 새로운 객체를 만드는게 아니다
}
func(a);
console.log(a.id);  // 2
```

파라미터 b는 객체 a의 레퍼런스다. 이 값의 속성을 바꾸면 그 속성이 소속된 객체를 대상으로 수정작업을 한 것이 되기 때문에 b의 변경은 a에도 영향을 미치게 된다. 

# 패턴

패턴은 자주 사용하는 로직들의 구현방법과 그것에 대한 이름을 의미한다. 이를 통해서 문제를 해결하는 탁월한 방법들을 빠르게 익힐 수 있다. 또한, 문제를 해결하기 위한 방법을 논의할 때 패턴의 이름을 사용함으로써 의사소통을 효율적으로 할 수 있다. 본 토픽의 하위 토픽을 통해서 다양한 패턴들을 알아본다. 

## 재귀함수

재귀함수는 함수 자신을 호출하는 프로그래밍 기법이다

# 수업을 마치며