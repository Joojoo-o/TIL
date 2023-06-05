# 📌 표기법

### dash-case (kebab-case)

html css에서 사용된다.
예시) the-quick-brown-fox-jumps-over-the-lazy-dog -기호를 띄어쓰기 대신 사용된다.
컴퓨터는 하나의 단어로 인식한다.

### snaake_case

html css에서 사용된다.
예시) the_quick_brown_fox_jumps_over_the_lazy_dog
언더슬래쉬 기호를 띄어쓰기 대신 사용한다.
컴퓨터는 하나의 단어로 인식한다.

### camelCase

js에서 사용된다.
예시) theQuickBrownFoxJumpsOverTheLazyDog
첫번째 글자는 소문자를 사용하고 다음단어의 첫글자는 대문자를 사용한다.
띄어쓰기는 사용하지 않는다.
대부분의 경우는 camelCase를 사용한다.

### ParcelCase

js에서 사용된다.
예시) TheQuickBrownFoxJumpsOverTheLazyDog
첫번째 글자도 대문자로 시작한다.

## Zero-based Numbering

0기반 번호 매기기!
특수한 경우를 제외하고 0부터 숫자를 시작한다.

요일에 대한 개념은 일요일이 0부터 시작하여 월요일은 1 ~ 토요일은 6으로 끝난다.

## 주석처리

js에서의 주석처리 방법
단축키 : ctrl /

```
// 한 줄 메모

/* 한 줄 매모 */

/**
 * 여러줄
 * 메모1
 * 메모2
 */

```

# 📌 데이터 종류 (자료형)

### string

> 문자데이터

`" "` `' '`
따옴표로 묶여있는 글자들이 하나의 문자 데이터 이다.
큰 따옴표와 작은 따옴표를 사용하며, 이 둘을 가리지 않는다.
` `` `
백틱 기호는 보간법의 기호이다.
예) let hello = 'Hello ${myname}?!'

### Number

> 숫자 데이터
> 정수 및 부동소수점 숫자를 나타낸다.

예) 123(정수), 1.57(부동소수점 숫자) 등
"123"은 안에 숫자가 있지만 숫자데이터로 인식하지 않고
"따옴표로 인해 문자데이터로 인식된다.

### Boolean

> 불린 데이터
> true, false 두 가지 값 밖에 없는 논리 데이터 이다.

true 진실
false 거짓

### Underfined

> 값이 할당되지(지정되지) 않은 상태를 나타낸다.

변수에 값을 주지 않아도 underfined데이터로 인식하여 하나의 데이터되어 출력 된다.

### Null

> 어떤 값이 **의도적**으로 비어있음을 의미한다.

예)

```
let empty = null;

console.log(empty); // null
```

### Object

> 객체 데이터
> 여러 데이터를 **Key:Value** 형태로 저장하는 데이터형태이다.
> {중괄호 사이에 데이터의 집합을 추가한다.}

```
예)
let user = {
  // Key: Value,
  name: 'HEROPY',
  age: 85,
  isValid: true
};

console.log(user.name); // HEROPY
console.log(user.age); // 85
console.log(user.isValid); // true

```

### Array

> 배열 데이터
> 여러 데이터를 순차적으로 저장한다.
> [대괄호 사이에 ,를 이용하여 순차적으로 입력한다.]

예)

```
let fruits = ['Apple', 'Banana', 'Cherry'};

console.log(fruits[0]); // 'Apple'
console.log(fruits[1]); // 'Banana'
console.log(fruits[2]); // 'Cherry'
```

# 📌 변수

데이터를 저장하고 참조(사용)하는 데이터의 이름
var(최근에는 권장하지 않음), let, const

### let

> 변수를 선언한다.
> (let 원하는이름명시 = 데이터입력; 하는 것을 변수를 선언한다고 한다.)
> 재사용이 가능하다.

예)

```
let a = 2;
let b = 5;

console.log(a + b); // 7
console.log(a - b); // -3
console.log(a * b); // 10
console.log(a / b); // 0.4
```

> 값(데이터)의 재할당이 가능하다.

let을 이용하여 변수를 선언한 후,
새로운 값으로 변수를 재 할당 할 수 있다.

```
let a = 12;
console.log(a); //12

a = 999;
console.log(a); //999
```

### const

> 변수를 선언한다.
> 재할당이 불가능 하다.

대부분의 경우에는 재할당이 불가한 **const를 주로 사용**하며,
재할당이 필요한 경우에만 let으로 수정 후 사용한다.

# 📌 예약어

> 특별한 의미를 가지고 있어, 변수나 함수 이름 등으로 사용할 수 없는 단어

Reserved Word

예)

```
let this = 'Hello!'; // SyntaxError문법에러
let if = 123; // SyntaxError
let brak = true; // SyntaxError
```

# 📌 함수

> 특정 동작(기능)을 수행하는 일부 코드의 집합(부분)

function

예)

```
// 함수 선언
function helloFunc() {
  // 실행 코드
  console.log(1234);
}

// 함수 호출
helloFunc(); // 1234



📍 return을 통해 js 데이터를 함수 밖으로 내보낼 수 있고
내보내진 값을 새로운 변수에 할당하여
추가적으로 사용할 수 있다.

function returnFunc() {
  return 123;
}

let a = returnFunc();

console.log(a); // 123




// 함수 선언
function sum(a, b) { //a와 b는 **🔎매개변수(PArameters)**
  return a + b;
}

// 재사용
let a = sum(1, 2); // 1과 2는 **🔎인수 (Arguments)**
let a = sum(7, 12);
let a = sum(2, 4);

console.log(a, b, c); //  3, 19, 6



// 🔎기명(이름이 있는) 함수
// 함수 **선언**
funxtion hello() {
  console.log('hello~');
}

// 🔎익명(이름이 없는) 함수
// (함수인 finction 뒷 부분에 이름이 없다. 데이터로 활용이 되거나 변수에 할당되어 활용되기도 한다.)
// 함수 **표현**
let world - function () {
  console.log('World~');
}

// 함수 호출
hello(); // Hello~
world(); // World~



// 객체 데이터
const heropy
  name: 'HEROPY'
  ageL 85,
  // 🔎메소드 (Method) - 속성 부분에 함수가 할당되어 있는 것
  getName: function () {
    return this.name; // this는 객체 데이터 내에 있는 name을 반환한다는 것을 의미한다.
  }
};

const hisName = heropy.getName();
console.log(hisName); // HEROPY
// 혹은
console.log(heropy.getName()); // HEROPY
```

# 📌 조건문

> 조건의 결과(truthy, falsy)에 따라 다른 코드를 실행하는 구문

if, else

예)

```
let isShow = true;
let checked = false;

🔎조건 블럭 / 조건문 / 조건 구문
if (isShow) {
  console.log('Show!'); // Show!
}

if (cheked) {
  console,log('Checked!'); // checked의 값은 false이므로 조건에 부합하지 않아 콘솔창에 뜨지 않는다.
}



let isShow = true;

if (isShow) {
  console.log('Show!');
} else {
  console.log('Hide?');
} // Show! 출력


let isShow = false;

if (isShow) {
  console.log('Show!');
} else {
  console.log('Hide?');
} // Hide? 출력
```

# 📌 DOM API

> 자바스크립트로 HTML을 제어하기 위해 사용하는 명령들

Document Object Model, Application Programming Interface
DOM : HTML의 div, span, input 요소
API : 웹사이트가 동작하기 위해 입력하는 프로그램 명령들

예)

```
[HTML]
🔎 head부분 먼저 해석이 된 후 실행되기 때문에 js에서 body부분에 작성한 코드를 읽지 못한다.
<head>
  <script src ="./main.js"></script>
</head>

🔎 defer을 추가 입력해주면 html을 모두 읽은 상태로 다시 main.js를 실행한다.
<head>
  <script defer src ="./main.js"></script>
</head>


🔎  HTML 요소(Element) 1개 검색/찾기
const boxEl = document.querySelector('.box');

🔎 HTML 요소에 적용할 수 있는 메소드
boxEl.addEventListener();

🔎  인수(Arguments)를 추가 가능
boEl. addEventListener(1,2);

🔎 1 - 이벤트(Event, 상황)
boxEl.addEventListener('click', 2);

🔎 2 - 핸들러(Handler, 실행할 함수)
boxEl.addEventListener('click', function () {
  console.log('Click~!');
});


🔎 HTML 요소(Element) 검색/찾기
const boxEl = document.quertSelector('.box);

🔎 요소의 클래스 정보 객체 활용
boxEl.classList.add('active');
let isContains = boxEl.classList.cintains('active');
console.log(isContains); // true

box.classList.remove('active');
isContains = boxEl.classList.contains('active');
console.log(isContains); //false


🔎 HTML 요소(Element) 모두 검색/찾기
const boxels = document.querySelectoerAll('.box');
console.log(boxEls);

🔎 찾은 요소들 반복해서 함수 실행
익명 함수를 인수로 추가
boxEls.forEach(function () {} );

🔎 첫번째 매개변수(boxEl): 반복 중인 요소
두번째 매개변수(index): 반복 중인 번호
boxEls.forEach(function (boxEl, inddex) {
  boxEl.classList.add(`oerder-${index +1}`);
  console.log(index, boxEl);
});



console boxEl = document.querySelector('.box');

🔎 Getter, 값을 얻는 용도
console.log(boxEl.textContent); // Box!!

🔎 Setter, 값을 지정하는 용도
boxEl.textContent = 'HEROPY?!';
console.log(boxEl.textContent); // HEROPY?!
```

# 📌 메소드 체이닝

Method Chaining

예)

```
const a = 'Hello~';
// split: 문자를 인수 기준으로 쪼개서 배열로 반환.
// reverse: 배열을 뒤집기.
// join: 배열을 인수 기준으로 문자로 병합해 반환.
const b = a.split('').reverse().join(''); // 메소드 체이닝

console.log(a); // Hello~
console.log(b); // ~olleH
```
