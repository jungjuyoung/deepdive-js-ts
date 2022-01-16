# 변수

변수는 하나의 값을 저장하기 위한 수단이다.

```javascript
var userId = 1;
var userName = "Lee";
```

변수는 하나의 값을 저장하기 위한 수단이다. 타입스크립트에서는 값의 타입을 변수에 적어준다.

```typescript
const userId: number = 1;
const userName: string = "Lee";
```

객체나 배열 같은 자료구조를 사용하면 여러 개의 값을 하나로 그룹화해서 하나의 값처럼 사용할 수 있다.

```javascript
var user = {id: 1, name: "Lee"};
var users = [
  {id: 1, name: "Lee"},
  {id: 2, name: "Kim"};
];
```

타입스크립트에서 Object는 Interface를 정의해 줘야한다.

```typescript
interface Iuser {
  id: number;
  name: string;
}

const user: Iuser = { id: 1, name: "Lee" };

const users: Array<Iuser> = [
  { id: 1, name: "Lee" },
  { id: 2, name: "Kim" },
];

const users2: Iuser[] = [
  { id: 1, name: "Lee" },
  { id: 2, name: "Kim" },
];
```

# 04-06

```javascript
var score; // 변수 선언
score = 80; // 값의 할당
```

# 선언문과 값의 할당

```javascript
var score = 80; // 변수 선언과 값의 할당
```

```javascript
console.log(score); // undefined

var score; // ① 변수 선언
score = 80; // ② 값의 할당

console.log(score); // 80
```

```javascript
console.log(score); // undefined

var score = 80; // 변수 선언과 값의 할당

console.log(score); // 80
```

```javascript
console.log(score); // undefined

score = 80; // 값의 할당
var score; // 변수 선언

console.log(score); // ??
```

```javascript
var score = 80; // 변수 선언과 값의 할당
score = 90; // 값의 재할당
```

변수선언시 권장되지 않는 문법 가독성을 위해 각각을 변수선언한다.
변수명은 영문으로

```javascript
var person, $elem, _name, first_name, val1;
```

```javascript
var 이름, なまえ;
```

변수명은 하이픈을 넣지 않는다. 연산자 마이너스로 혼동해 에러를 낸다.
첫글자가 숫자가 오지 않는다
예약어를 사용하지 않는다.

```javascript
var first-name; // SyntaxError: Unexpected token –
var 1st;        // SyntaxError: Invalid or unexpected token
var this;       // SyntaxError: Unexpected token this
```

```javascript
var firstname;
var firstName;
var FIRSTNAME;
```

```javascript
var x = 3; // NG. x 변수가 의미하는 바를 알 수 없다.
var score = 100; // OK. score 변수는 점수를 의미한다.
```

```javascript
// 경과 시간. 단위는 날짜다
var d; // NG

var elapsedTimeInDays; // OK
```

# 변수선언문의 종류

```javascript
// 카멜 케이스 (camelCase)
var firstName;

// 스네이크 케이스 (snake_case)
var first_name;

// 파스칼 케이스 (PascalCase)
var FirstName;

// 헝가리언 케이스 (typeHungarianCase)
var strFirstName; // type + identifier
var $elem = document.getElementById("myId"); // DOM 노드
var observable$ = fromEvent(document, "click"); // RxJS 옵저버블
```

# 05-01

```javascript
// 10 + 20은 평가되어 숫자 값 30을 생성한다.
10 + 20; // 30
```

# 05-02

```javascript
// 변수에는 10 + 20이 평가되어 생성된 숫자 값 30이 할당된다.
var sum = 10 + 20;
```

# 05-03

```javascript
// 숫자 리터럴 3
3;
```

# 05-04

```javascript
var score = 100;
```

# 05-05

```javascript
var score = 50 + 50;
```

# 05-06

```javascript
score; // -> 100
```

# 05-07

```javascript
// 리터럴 표현식
10;
("Hello");

// 식별자 표현식(선언이 이미 존재한다고 가정)
sum;
person.name;
arr[1];

// 연산자 표현식
10 + 20;
sum = 10;
sum !== 10;

// 함수/메서드 호출 표현식(선언이 이미 존재한다고 가정)
square();
person.getName();
```

# 05-08

```javascript
var x = 1 + 2;

// 식별자 표현식 x는 3으로 평가된다.
x + 3; // -> 6
```

# 05-09

```javascript
// 변수 선언문
var x;

// 표현식 문(할당문)
x = 5;

// 함수 선언문
함수는 1급 객체로 변수에 할당가능한 값.
function foo() {}

// 조건문
변수에 할당 불가능
if (x > 1) {
  console.log(x);
}

// 반복문
변수에 할당 불가능
for (var i = 0; i < 2; i++) {
  console.log(i);
}
```

# 05-10

```javascript
function foo() {
  return;
  {
  }
  // ASI의 동작 결과 => return; {};
  // 개발자의 예측 => return {};
}

console.log(foo()); // undefined

var bar = (function () {})(function () {})();
// ASI의 동작 결과 => var bar = function () {}(function() {})();
// 개발자의 예측 => var bar = function () {}; (function() {})();
// TypeError: (intermediate value)(...) is not a function
```

```javascript
// 변수 선언문은 값으로 평가될 수 없으므로 표현식이 아니다.
var x;
// 1, 2, 1 + 2, x = 1 + 2는 모두 표현식이다.
// x = 1 + 2는 표현식이면서 완전한 문이기도 하다.
x = 1 + 2;
```

```javascript
// 표현식이 아닌 문은 값처럼 사용할 수 없다.
var foo = var x; // SyntaxError: Unexpected token var
```

# 05-13

```javascript
// 변수 선언문은 표현식이 아닌 문이다.
var x;

// 할당문은 그 자체가 표현식이지만 완전한 문이기도 하다. 즉, 할당문은 표현식인 문이다.
x = 100;
```

```javascript
// 표현식인 문은 값처럼 사용할 수 있다
var foo = (x = 100);
// ? var foo = x = 100;
console.log(foo); // 100
```
