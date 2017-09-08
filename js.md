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


함수호출 : 기존의 함수호출 방식말고 함수.apply()나 .call()을 통해서도 함수를 호출할 수 있다.
- 함수.apply(null, [a, b...]) [a,b...}에 함수에 인자의 값이 들어간다.
- null에 자리에는 객체 등이 들어 가는데 apply()를 쓰는 상황은 this를 사용하는 독립적인 함수가 있을 때
apply를 사용해서 매 번 다른 객체를 넣어주면 함수가 그 객체의 메소드처럼 사용된다.
쉽게 말하자면 여러 객체에서 쓸 수 있는 공용함수처럼 쓰기 위해서 만들어진 기법인 듯하다.


# 객체지향
## 객체지향 프로그래밍
## 생성자와 new
## 전역객체
## this
## 상속
## prototype
## 표준 내장 객체의 확장
## Object
## 데이터 타입
## 참조
# 패턴
## 재귀함수
# 수업을 마치며