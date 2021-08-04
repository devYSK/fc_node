# fc_node
fastcampus_node
 

# [1.Javascript(박준영)](#1.Javascript(박준영)) 


## 1.Javascript(박준영)
 
## 
## Javascript란

브라우저 제어하기 위해 넷스케이프에서 개발한 언어
사용자의 클릭, 계산기, 달력 등의 이벤트 조작에 대응하기 위한 언어.  
* 자바스크립트의 확대
  * AJAX 활용(구글맵) -> Debug툴에 발전 -> V8엔진의 개발 -> Node.js 등장 -> Desktop, IOT, 사용범위 확대 


### 변수선언
* var 로 선언 (var a = 1;)
* 동적언어 이므로 자료형을 선언할 필요 없음
* 기본자료형(primitive)와 객체(Object)[레퍼런스?]로 나뉜다
  * boolean : 논리적 자료형
  * Null : 널
  * Undefined : 값을 할당하지 않음
  * Number : 숫자형
  * String : 문자형
  * Symbol : ES6에서 추가, 유일하고 변경 불가

* vscode html 파일 팁
  * ! 쓰고 탭 누르면 기본 헤더부터 바디까지 기본 틀이 만들어진다!



* undefiend 형은 오류가 아니고 그냥 빈 자료형이다.
* null이랑 undefined형은 다르다.

---
## 2.배열

var a = ['안녕', 'Node.js', 55, 'Hello']
* 자바 스크립트의 배열은 자료형이 따로 필요 없다. 
* 배열의 끝에 값을 계속 추가할 수 있다. ex) size가 3인 a 배열의 a[3] = 새 값;

* 선언법
  * var array = new Array("1111", "22");
  * var array = [];

---

## 3. 반복문
1. for
2. while
3. do-while

---
## 4. 함수


```javascript
function test() {
    ...
}

var func = test(); // 이런식으로 함수를 담을수도 있다.


// 이런식으로 익명함수도 호출할 수 있다. 
var sum = fuction(name, name2) {
    return "이건 익명함수 " + name + ", " + name2;
}

var sum2 = sum(); // sum 과 sum2는 같다. 

function Car(a, b, c) {
    this.name = a; // 멤버변수, 공용변수이다 접근가능
    this.color = b; // 멤버변수, 퍼블릭변수 
    var move = c; // 내부에서만 사용가능. 프라이빗 변수 

}
// 함수를 만들고 객체를 찍어낸것

var a = new Car("현대자동차", "black", "천천히");

console.log(a.name); // 멤버변수에 접근 
console.log(a.color); // 멤버변수에 접근 
console.log(a.move); // 변수에 접근불가. 프라이빗 변수. 언디파인드라고 나옴

var b = new Car("기아", "blue", "빠름");
console.log(b.name); // 멤버변수에 접근 
console.log(b.color); // 멤버변수에 접근 
console.log(b.move); // 변수에 접근불가. 프라이빗 변수. 언디파인드라고 나옴  


// 프로토타입
/////////// 함수 선언
 
Car.prototype.move2 = function() {
    console.log(this.name + "차이고  " + this.color + "색입니다.");
} 

var a = new Car("현대자동차", "black", "천천히");
a.move(); // 함수 사용 가능. 메서드와 비슷한 개념? 

// 이런식으로도 사용 가능
var a = [1, 2, 3, 4, 5, 10];
Array.prototype.print = function() {
    for (var i = 0; i < this.length; i++) {
        console.log(i);
    }
}

a.print(); // 이런식으로 함수를 만들어 사용 가능. 기본에 덮어서 기능을 추가할 수 있다.

```
* new 키워드는 객체를 새로 생성하는것. 

----

## 5. 리터럴 객체
객체 생성 방법. 
* {} 중괄호로 선언.   
* 배열이랑 차이점은 인덱스를 자기가 정한다.
* 선언과 동시에 생성이 되는 리터럴 객체(object) 이다. new와는 다른 방법의 객체 생성 방법.

* 객체 리터럴의 중괄호({})는 코드 블록 의미하지 않는다. 코드 블록의 닫는 중괄호 뒤에는 세미콜론(;)이 오지 않는다.

* https://velog.io/@jimmyjoo/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EA%B0%9D%EC%B2%B4%EB%A6%AC%ED%84%B0%EB%9F%B4 참고 

```javascript
var a = {
    'a' : 110, // 리터럴 객체의 멤버변수
    'b' : 'hello', // 리터럴 객체의 멤버변수 
    'c' : function() {
        console.log("gggg");
        console.log(this.a); // 멤버변수에 접근 가능. 
        this.a++;
    }
}

console.log(a.a); // 110 출력
console.log(a.b); // hello 출력
a.c(); // 객체의 함수 사용 

console.log(typeof a); // object 출력

// 위와 같이 프로토타입에 접근하여 함수(기능) 추가.
Object.prototype.sum = function() {
    console.log(this.a + 20);
}

a.sum(); // console.log() 실행됨 
a.c();

```

---

## 6. 조건문

```javascript
var a = 5;

if (a < 10) {
    console.log('10보다 작다잉');
} else {
    console.log('10보다 크다잉');
}

if (a === 5) { // js의 === 은 값과, 형태(타입)까지 같다는 의미. 
    ...
}

switch("yello") { // 문자열, 숫자 가능 
    case "blue" : 
        console.log("blue");
        break;
    case "green" :
        console.log("yello");
        break;

    default : 
        console.log("default!");
}

function myNum(num) {
    if (num < 10) {
        return "10보다 작음";
    } else {
        return "10보다 큼";
    }
}

var test = myNum(15);
console.log(test); // 10보다 큼 이라는 문자열 리턴 

```

---
## 7. 콜백함수 및 클로저

콜백함수 :  콜백함수(Callback Function)란 파라미터로 함수를 전달받아, 함수의 내부에서 실행하는 함수이다.


클로저 : 함수내에서 변수를 메모리처럼 사용하는것. 리턴을 익명함수로. 

```javascript

// 콜백함수 예제
function test(num, callback) {
    console.log(num);
    callback();
}

test(1, function() {
    console.log('콜백함수 실행');
});


// 클로저 예제 

function ex_cl() {
    var num = 0;
    return function() {
        num++;
        console.log(num);
    }

    // 이런식으로도 사용 가능 위와 아래는 리턴방법만 다른것. 
    var innerFunc = function() {
        num++;
        console.log(num); 
    }
    return innerFunc;
}

var test = ex_cl();
test(); // 여기서는 num이 1
test(); // 여기서는 num이 2. 2번 호출했기 때문. 

```

// 클로저 관련 블로그 예제
```javascript
function outerFunc() {
  var x = 10;
  var innerFunc = function () { console.log(x); };
  return innerFunc;
}

/**
 *  함수 outerFunc를 호출하면 내부 함수 innerFunc가 반환된다.
 *  그리고 함수 outerFunc의 실행 컨텍스트는 소멸한다.
 */
var inner = outerFunc();
inner(); // 10
```

* 이처럼 자신을 포함하고 있는 외부함수보다 내부함수가 더 오래 유지되는 경우, 외부 함수 밖에서 내부함수가 호출되더라도 외부함수의 지역 변수에 접근할 수 있는데 이러한 함수를 클로저(Closure)라고 부른다.

* 위 정의에서 말하는 “함수”란 반환된 내부함수를 의미하고 “그 함수가 선언될 때의 렉시컬 환경(Lexical environment)”란 내부 함수가 선언됐을 때의 스코프를 의미한다. 즉, 클로저는 반환된 내부함수가 자신이 선언됐을 때의 환경(Lexical environment)인 스코프를 기억하여 자신이 선언됐을 때의 환경(스코프) 밖에서 호출되어도 그 환경(스코프)에 접근할 수 있는 함수를 말한다. 이를 조금 더 간단히 말하면 클로저는 자신이 생성될 때의 환경(Lexical environment)을 기억하는 함수다라고 말할 수 있겠다.


* 참조 : https://poiemaweb.com/js-closure


## 