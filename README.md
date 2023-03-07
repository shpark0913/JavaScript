### 개요

- 웹 브라우저의 역할
  - URL을 통해 Web(WWW)을 탐색함
  - **HTML / CSS / JavaScript 를 이해한 뒤 해석**해서 사용자에게 하나의 화면으로 보여줌
  - 웹 서비스 이용 시 클라이언트의 역할을 함
  - 즉, 웹 페이지 코드를 이해하고, 보여주는 역할을 하는 것이 웹 브라우저
- 웹 브라우저는 JavaScript를 해석하는 엔진을 가지고 있음
- 현재의 JavaScript는 이제 시장에서 자리를 잡은 언어이며, 개발에서 큰 축을 담당함
- 특히 Chrome V8의 경우 JavaScript를 번역하는 속도가 매우 빠름
  - node.js, react.js, electron 등의 내부 엔진으로 사용됨
  - 그 결과 BE, mobile, desktop app 등을 모두 JavaScript로 개발이 가능해짐

---

### JavaScript 코드 작성법

- 세미콜론 (semicolon)
  
  - 자바스크립트는 세미콜론을 선택적으로 사용 가능
  - 세미콜론이 없으면 ASI에 의해 자동으로 세미콜론이 삽입됨
    - ASI ( Automatic Semicolon Insertion, 자동 세미콜론 삽입 규칙)
  
  ```jsx
  console.log('hello');
  console.log('javascript')
  ```

---

- 들여쓰기와 코드 블럭
  
  - JavaScript는 2칸 들여쓰기를 사용
  - **블럭(block)**은 **if, for, 함수에서 중괄호 { } 내부**를 말함
    - JavaScript는 중괄호 { }를 사용해 코드 블럭을 구분
  
  ```jsx
  if (isClean) { // 중괄호를 사용해서 코드 블럭 구분
   console.log('clean!')  // 2칸 들여쓰기
  }
  ```

---

- 주석
  
  - // : 한 줄 주석
  - /* */ : 여러 줄 주석
  
  ```jsx
  // console.log('화면에 표시되지 않음')
  
  /* 
  여러 줄 주석은
  이렇게 사용합니다.
  */
  ```

---

- 변수와 식별자
  - 식별자(identifier)는 변수를 구분할 수 있는 변수명을 말함
  - 식별자는 반드시 `문자, $, _` 로 시작
  - 대소문자를 구분하며, 클래스명 외에는 모두 소문자로 시작
  - 예약어 사용 불가능
    - 예약어 예시 : for, if, function 등

---

- 식별자 정의와 특징
  
  - 카멜 케이스 (camelCase, lower-camel-case)
    
    - 변수, 객체, 함수에 사용
    
    ```jsx
    // 변수
    let dog
    let variableName
    
    // 객체
    const userInfo = { name: 'Tom', age: 20 }
    
    // 함수
    function add() {}
    function getName() {}
    ```
  
  - 파스칼 케이스 (PascalCase, upper-camel-case)
    
    - 클래스, 생성자에 사용
    
    ```jsx
    // 클래스
    class User {
        constructor(options) {
            this.name = options.name
        }
    }
    
    // 생성자 함수
    function User(options) {
        this.name = options.name
    }
    ```
  
  - 대문자 스네이크 케이스 (SNAKE_CASE)
    
    - 상수 (constants)에 사용
    - 상수 : 개발자의 의도와 상관없이 변경될 가능성이 없는 값을 의미
    
    ```jsx
    // 값이 바뀌지 않을 상수
    const API_KEY = 'my-key'
    const PI = Math.PI
    
    // 재할당이 일어나지 않는 변수
    const NUMBERS = [1, 2, 3]
    ```

---

- 변수 선언 키워드
  
  - `let`
    
    - 블록 스코프 지역 변수를 선언
      - 추가로 동시에 값을 초기화
  
  - `const`
    
    - 블록 스코프 읽기 전용 상수를 선언
      - 추가로 동시에 값을 초기화
  
  - `var`
    
    - 변수를 선언
      - 추가로 동시에 값을 초기화
  
  - 참고) 선언, 할당, 초기화
    
    - 선언 (Declaration)
      - 변수를 생성하는 행위 또는 시점
    - 할당 (Assignment)
      - 선언된 변수에 값을 저장하는 행위 또는 시점
    - 초기화 (Initialization)
      - 선언된 변수에 처음으로 값을 저장하는 행위 또는 시점
    
    ```jsx
    let foo            // 선언
    console.log(foo)   // undefined
    
    foo = 11           // 할당
    console.log(foo)   // 11
    
    let bar = 0        // 선언 + 할당
    console.log(bar)   // 0
    ```
  
  - 참고) 블록 스코프(block scope)
    
    - **if, for, 함수** 등의 중괄호 { } 내부를 가리킴
    - 블록 스코프를 가지는 변수는 블록 바깥에서 접근 불가능
    
    ```jsx
    let x = 1;
    
    if (x === 1) {
        let x = 2
        console.log(x)   // 2
    }
    
    console.log(x)     // 1
    ```

---

- 변수 선언 키워드 - let
  
  - let
    
    - 재할당 가능 & 재선언 불가능
    
    ```jsx
    let number = 10    // 1. 선언 및 초기값 할당
    number = 20        // 2. 재할당
    ```
    
    ```jsx
    let number = 10    // 1. 선언 및 초기값 할당
    let number = 20    // 2. 재선언 불가능
    ```
    
    - 블록 스코프를 갖는 지역 변수를 선언, 선언과 동시에 원하는 값으로 초기화 할 수 있음

---

- 변수 선원 키워드 - const
  
  - const
    
    - 재할당 불가능 & 재선언 불가능
    
    ```jsx
    const number = 10   // 1. 선언 및 초기값 할당
    number = 20         // 2. 재할당 불가능
    ```
    
    ```jsx
    const number = 10   // 1. 선언 및 초기값 할당
    const number = 20   // 2. 재선언 불가능
    ```
    
    - 선언 시 반드시 초기값을 설정해야 하며, 이후 값 변경이 불가능
    - let 과 동일하게 블록 스코프를 가짐

---

- 변수 선언 키워드 - var
  
  - var
    
    - 재할당 가능 & 재선언 가능
    
    - ES6 이전에 변수를 선언할 때 사용되던 키워드
    
    - `호이스팅` 되는 특성으로 인해 예기치 못한 문제 발생 가능
      
      - ES6 이후부터는 var 대신 const 와 let 을 사용하는 것을 권장
    
    - 함수 스코프를 가짐
      
      - 함수의 중괄호 내부를 가리킴
      - 함수 스코프를 가지는 변수는 함수 바깥에서 접근 불가능
      
      ```jsx
      function foo() {
          var x = 5
          console.log(x)    // 5
      }
      
      // ReferenceError : x is not defined
      console.log(x)
      ```
    
    - 변수 선언 시 var, const, let 키워드 중 하나를 사용하지 않으면 자동으로 var로 선언됨
  
  - 참고) 호이스팅 ( hoisting )
    
    - 변수를 선언 이전에 참조할 수 있는 현상
    - var로 선언된 변수는 선언 이전에 참조할 수 있으며, 이러한 현상을 호이스팅이라 함
    - 변수 선언 이전의 위치에서 접근 시 undefined를 반환
    
    ```jsx
    console.log(name)   // undefined => 선언 이전에 참조
    
    var name = '홍길동'  // 선언
    ```
    
    ```jsx
    // 위 코드를 암묵적으로 아래와 같이 이해함
    var name      // undefined로 초기화
    console.log(name)
    
    var name = '홍길동'
    ```
    
    - JavaScript에서 변수들은 실제 실행 시에 코드의 최상단으로 끌어올려지게 되며 (hoisted) 이러한 이유 때문에 var로 선언된 변수는 선언 시에 undefined로 값이 초기화되는 과정이 동시에 일어남
    - 반면 let, const는 호이스팅이 일어나면 에러를 발생시킴
    - 변수를 선언하기 전에 접근이 가능한 것은 코드의 논리적인 흐름을 깨뜨리는 행위이며 이러한 것을 방지하기 위해 let, const가 추가되었음
      - 즉, `var는 사용하지 않아야 하는 키워드`

---

- 변수 선언 키워드 정리
  
  | 키워드   | 재선언 | 재할당 | 스코프    | 비고       |
  | ----- | --- | --- | ------ | -------- |
  | let   | X   | O   | 블록 스코프 | ES6부터 도입 |
  | const | X   | X   | 블록 스코프 | ES6부터 도입 |
  | var   | O   | O   | 함수 스코프 | 사용 X     |

---

- 데이터 타입
  
  - JavaScript의 모든 값은 특정한 데이터 타입을 가짐
  - 크게 **원시 타입(Primitive type)**과 **참조 타입(Reference type)**으로 분류됨
  
  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0b965550-7de5-44fa-844c-0b5096b38196/Untitled.png)

---

- Number
  
  - 정수 또는 실수형 숫자를 표현하는 자료형
  
  ```jsx
  const a = 13
  const b = -5
  const c = 3.14      // float - 숫자 표현
  const d = 2.998e8   // 2.998 * 10^8 = 299,800,000
  const e = Infinity
  const f = -Infinity
  const g = NaN       // Not a Number 을 나타내는 값
  ```
  
  - NaN
    
    - Not-A-Number(숫자가 아님)를 나타냄
    
    - `Number.isNaN()`의 경우 주어진 값의 유형이 Number이고
      
      - 값이 NaN이면 true
      - 아니면 false
      
      반환
    
    ```jsx
    console.log(Number.isNaN(NaN))       // true
    console.log(Number.isNaN(0 / 0))     // true
    console.log('#####################');
    
    // isNaN() 으로는 True  => Number 이면서 NaN 인지 아닌지 판별
    console.log(Number.isNaN('NaN'))     // false
    console.log(Number.isNaN(undefined)) // false
    console.log(Number.isNaN({}))        // false
    console.log(Number.isNaN('blabla'))  // false
    console.log('#####################');
    
    // isNaN() 으로도 해보기 => NaN 인지 아닌지 판별
    console.log(isNaN('NaN'))            // true
    console.log(isNaN(undefined))        // true
    console.log(isNaN({}))               // true
    console.log(isNaN('blabla'))         // true
    console.log('#####################');
    
    // 이들 모두 false
    console.log(Number.isNaN(true))
    console.log(Number.isNaN(null))
    console.log(Number.isNaN(37))
    console.log(Number.isNaN('37'))
    console.log(Number.isNaN('37.37'))
    console.log(Number.isNaN(''))
    console.log(Number.isNaN(' '))
    ```
    
    - NaN을 반환하는 경우
      1. 숫자로서 읽을 수 없음
         - parseInt(”어쩌구”), Number(undefined)
      2. 결과가 허수인 수학 계산식
         - Math.sqrt(-1)
      3. 피연산자가 NaN
         - 7 * NaN
      4. 정의할 수 없는 계산식
         - 0 * Infinity
      5. 문자열을 포함하면서 덧셈이 아닌 계산식
         - “가” / 3

---

- String
  
  - 문자열을 표현하는 자료형
  
  - 작은 따옴표 또는 큰 따옴표 모두 가능
  
  - 곱셈, 나눗셈, 뺄셈은 안되지만 덧셈을 통해 문자열 붙일 수 있음
  
  - Quote를 사용하면 선언 시 줄 바꿈이 안됨
  
  - 대신 escape sequence를 사용할 수 있기 때문에 \n를 사용해야 함
    
    ```jsx
    // Bad
    const word = "안녕
    하세요"   // Uncaught SyntaxError : Invalid or unexpected token
    
    // Good
    const word1 = "안녕 \\n 하세요"
    console.log(word1)
    ```
  
  - **Template Literal**을 사용하면 줄 바꿈이 되며, 문자열 사이에 변수도 삽입 가능
    
    - 단, escape sequence를 사용할 수 없다
      
      === Python의 “f-string”
    
    ```jsx
    const word2 = `안녕
    들 하세요`
    console.log(word2)
    
    const age = 10
    const message = `홍길동은 ${age}세입니다.`
    console.log(message)
    ```
    
    ---
    
    - Template literals (템플릿 리터럴)
      
      - 내장된 표현식을 허용하는 문자열 작성 방식
      
      - Backtick(``)을 이용하며, 여러 줄에 걸쳐 문자열을 정의할 수도 있고 JavaScript의 변수를 문자열 안에 바로 연결할 수 있는 이점이 생김
      
      - 표현식을 넣을 수 있는데, 이는 $와 중괄호로 표기
        
        ```jsx
        const age = 10
        const message = `홍길동은 ${age}세입니다.`
        ```

---

- Empty Value
  
  - 값이 존재하지 않음을 표현하는 값으로 JavaScript에서는 `null`과 `undefined` 가 존재
  - 동일한 역할을 하는 이 2개의 키워드가 존재하는 이유는 단순한 JavaScript의 설계 실수
  - 큰 차이를 두지 말고 interchangeable 하게 사용할 수 있도록 권장함
  
  ---
  
  - null
    
    - null 값을 나타내는 특별한 키워드
    
    - 변수의 **값이 없음을 의도적으로 표현**할 때 사용하는 데이터 타입
      
      ```jsx
      let lastName = null
      console.log(lastName)   // null
      ```
  
  - undefined
    
    - 값이 정의되어 있지 않음을 표현하는 값
    
    - 변수 선언 이후 직접 값을 할당하지 않으면 자동으로 할당됨
      
      ```jsx
      let firstName           // 선언만 하고 할당하지 않음
      console.log(firstName)  // undefined
      ```
  
  - null과 undefined
    
    - null과 undefined의 가장 대표적인 차이점은 `typeof` 연산자를 통해 타입을 확인했을 때 나타남
      
      ```jsx
      typeof null      // "object"
      typeof undefined // "undefined"
      ```
    
    - null이 원시 타입임에도 불구하고 object로 출력되는 이유는 JavaScript 설계 당시의 버그를 지금까지 해결하지 못한 것
    
    - 쉽게 해결할 수 없는 이유는 이미 null 타입에 의존성을 띄고 있는 많은 프로그램들이 망가질 수 있기 때문 ( 하위 호환 유지 )

---

- Boolean
  
  - true와 false
  
  - 참과 거짓을 표현하는 값
  
  - 조건문 또는 반복문에서 유용하게 사용
    
    - 조건문 또는 반복문에서 boolean이 아닌 데이터 타입은 `자동 형변환 규칙` 에 따라 true 또는 false로 변환됨
      
      - 자동 형변환 규칙
        
        | 데이터 타입    | false      | true      |
        | --------- | ---------- | --------- |
        | undefined | 항상 false   | X         |
        | null      | 항상 false   | X         |
        | Number    | 0, -0, NaN | 나머지 모든 경우 |
        | String    | 빈 문자열      | 나머지 모든 경우 |
        | Object    | X          | 항상 true   |

---

- 연산자
  
  - 할당 연산자
    
    - 오른쪽에 있는 피연산자의 평가 결과를 왼쪽 피연산자에 할당하는 연산자
    - 다양한 연산에 대한 단축 연산자 지원
    - Increment 및 Decrement 연산자
      - Increment(++) : 피연산자의 값을 1 증가시키는 연산자
      - Decrement(- -) : 피연산자의 값을 1 감소시키는 연산자
      - += 또는 -= 와 같이 더 분명한 표현을 권장함
  
  - 비교 연산자
    
    - 피연산자들(숫자, 문자, Boolean 등)을 비교하고 결과값을 boolean으로 반환하는 연산자
    
    - 문자열은 유니코드 값을 사용하며 표준 사전 순서를 기반으로 비교
      
      - 알파벳끼리 비교할 경우
        
        - 알파벳 순서상 후순위가 더 크다
        - 소문자가 대문자보다 더 크다
        
        ```jsx
        3 > 2         // true
        3 < 2         // false
        
        'A' < 'B'     // true
        'Z' < 'a'     // true
        '가' < '나'    // true
        ```
  
  - 동등 연산자(==)
    
    - 두 피연산자가 같은 값으로 평가되는지 비교 후 boolean 값을 반환
    - 비교할 때 `암묵적 타입 변환` 을 통해 타입을 일치시킨 후 같은 값인지 비교
    - 두 피연산자가 모두 객체일 경우 메모리의 같은 객체를 바라보는지 판별
    - ****************************************************************************************************************************************************************************************************************예상치 못한 결과가 발생할 수 있으므로 특별한 경우를 제외하고 사용하지 않음****************************************************************************************************************************************************************************************************************
  
  - 일치 연산자(===)
    
    - 두 피연산자의 값과 타입이 모두 같은 경우 true를 반환
    - 같은 객체를 가리키거나, 같은 타입이면서 같은 값인지를 비교
    - 엄격한 비교가 이뤄지며 `암묵적 타입 변환이 발생하지 않음`
      - 엄격한 비교 - 두 비교 대상의 타입과 값 모두 같은지 비교하는 방식
  
  - 논리 연산자
    
    - 세 가지 논리 연산자로 구성
      - and 연산 : &&
      - or 연산 : ||
      - not 연산 : !
    - 단축 평가 지원
      - ex) false && true ⇒ false
      - ex) true || false ⇒ true
  
  - 삼항 연산자
    
    - 3개의 피연산자를 사용하며 조건에 따라 값을 반환하는 연산자
    - 가장 앞의 조건식이 참이면 :(콜론) 앞의 값이 반환되며, 그 반대일 경우 : 뒤의 값이 반환되는 연산자
    - 삼항 연산자의 결과값이기 때문에 변수에 할당 가능
    
    ```jsx
    true? 1:2     // 1
    false: 1:2    // 2
    
    const result = Math.PI > 4 ? 'Yep' : 'Nope'
    console.log(result)    // Nope
    ```

---

- 조건문
  - 조건문의 종류와 특징
    - if
      - 조건 표현식의 결과값을 `boolean 타입으로 변환 후 참/거짓을 판단`
    - switch
      - 조건 표현식의 결과값이 `어느 값(case)에 해당하는지 판별`
      - 주로 특정 변수의 값에 따라 조건을 분기할 때 활용
        - 조건이 많아질 경우 if 문보다 가독성이 나을 수 있음

---

- if statement
  
  - if, else if, else
    
    - 조건은 소괄호 안에 작성
    - 실행할 코드는 중괄호 안에 작성
    - 블록 스코프 생성
    
    ```jsx
    const name = 'manager'
    
    if (name === 'admin') {
        console.log('관리자님 환영합니다.')
    } else if (name === 'manager') {
        console.log('매니저님 환영합니다.')
    } else {
        console.log(`${name}님 환영합니다.`)
    }
    ```

- switch statement
  
  - 표현식의 결과값을 이용한 조건문
  - 표현식의 결과값과 case 문의 오른쪽 값을 비교
  - break 및 default 문은 [선택적]으로 사용 가능
  - break 문이 없는 경우 break 문을 만나거나 default 문을 실행할 때까지 다음 조건문 실행
  - 블록 스코프 생성
  
  ```jsx
  switch(expression) {
      case 'first value': {
          // do something
          [break]
      }
      case 'second value': {
          //do something
          [break]
      }
      [default: {
          //do something
      }]
  }
  ```
  
  - 이 경우 모든 console이 출력됨 (**Fall-through 현상**)
    
    ```jsx
    const name = '홍길동'
    
    switch(name) {
        case '홍길동': {
            console.log('관리자님 환영합니다.')
        }
        case 'manager': {
            console.log('매니저님 환영합니다.')
        default: {
            console.log(`${name}님 환영합니다.`)
        }
    }
    
    // 출력 결과
    관리자님 환영합니다.
    매니저님 환영합니다.
    홍길동님 환영합니다.
    ```
    
    - break를 작성하면 의도한 대로 동작
    
    ```jsx
    const name = '홍길동'
    
    switch(name) {
        case '홍길동': {
            console.log('관리자님 환영합니다.')
            break
        }
        case 'manager': {
            console.log('매니저님 환영합니다.')
            break
        default: {
            console.log(`${name}님 환영합니다.`)
        }
    }
    
    // 출력 결과
    관리자님 환영합니다.
    ```

- if / switch
  
  - 조건이 많은 경우 switch문을 통해 가독성 향상을 기대할 수 있음
  - 일반적으로 중첩 else if 문은 유지보수하기 힘들다는 문제가 있음

---

- 반복문
  
  - 종류
    
    - while
    - for
    - for … in
    - for … of
  
  - while
    
    - 조건문이 참이기만 하면 문장을 계속해서 수행
      
      ```jsx
      while (조건문) {
          // do something
      }
      ```
      
      예시)
      
      ```jsx
      let i = 0
      
      while (i < 6) {
          console.log(i)
          i += 1
      }
      
      // 0, 1, 2, 3, 4, 5
      ```
  
  - for
    
    - 특정한 조건이 거짓으로 판별될 때까지 반복
      
      ```jsx
      for ( [초기문]; [조건문]; [증감문]) {
          console.log(i)
      }
      
      // 0, 1, 2, 3, 4, 5
      ```
  
  - for … in
    
    - 객체 (object) 의 **속성을 순회**할 때 사용
    - 배열도 순회 가능하지만 인덱스 순으로 순회한다는 보장이 없으므로 권장하지 않음
    
    ```jsx
    for (variable in object) {
        statements
    }
    ```
    
    예시)
    
    ```jsx
    const fruits = { a: 'apple', b: 'banana' }
    
    for (const key in fruits) {
        console.log(key)          // a, b
        console.log(fruits[key])  // apple, banana
    }
    ```
  
  - for … of
    
    - 반복 가능한 객체를 순회할 때 사용
    - 반복 가능한 (iterable) 객체의 종류 : `Array, Set, String` 등 ( Object는 TypeError )
    
    ```jsx
    for (variable of object) {
        statements
    }
    ```
    
    예시)
    
    ```jsx
    const numbers = [0, 1, 2, 3]
    
    for (const number of numbers) {
        console.log(number)   // 0, 1, 2, 3
    }
    ```
  
  - for … in 과 for … of 의 차이
    
    - for … in 은 `속성 이름` 을 통해 반복
    - for … of 는 `속성 값` 을 통해 반복
    
    ```jsx
    const arr = [3, 5, 7]
    
    for (const i in arr) {
        console.log(i)     // 0 1 2
    }
    
    for (const i of arr) {
        console.log(i)     // 3 5 7
    }
    ```
    
    - for … in 은 객체 순회 적합
      
      ```jsx
      // Array
      const numbers = [10, 20, 30]
      for (const number in numbers) {
          console.log(number)       // 0 1 2
      }
      
      // Object
      const capitals = {
          korea: '서울',
          france: '파리',
          japan: '도쿄'
      }
      for (const capital in capitals) {
          console.log(capital)    // korea france japan
      }
      ```
    
    - for … of 는 Iterable 순회 적합
      
      ```jsx
      // Array
      const numbers = [10, 20, 30]
      for (const number in numbers) {
          console.log(number)       // 10 20 30 
      }
      
      // Object
      const capitals = {
          korea: '서울',
          france: '파리',
          japan: '도쿄'
      }
      for (const capital in capitals) {
          console.log(capital)    // TypeError : capitals is not iterable
      }
      ```
    
    - 참고) for … in, for … of 와 const
      
      - for 문
        - for ( let i = 0; i < arr.length; i++ ) { … } 의 경우 최초 정의한 i 를 재할당하면서 사용하기 때문에 const를 사용하면 `에러 발생`
      - for … in, for … of
        - 재할당이 아니라, 매 반복 시 해당 변수를 새로 정의하여 사용하므로 `에러가 발생하지 않음`
  
  - 조건문과 반복문 정리
    
    | 키워드      | 종류  | 연관 키워드               | 스코프    |
    | -------- | --- | -------------------- | ------ |
    | if       | 조건문 | -                    | 블록 스코프 |
    | switch   | 조건문 | case, break, default | 블록 스코프 |
    | while    | 반복문 | break, continue      | 블록 스코프 |
    | for      | 반복문 | break, continue      | 블록 스코프 |
    | for … in | 반복문 | 객체 순회                | 블록 스코프 |
    | for … of | 반복문 | Iterable 순회          | 블록 스코프 |

---

### 함수

- 참조 타입 중 하나로써 function 타입에 속함
- JavaScript에서 함수를 정의하는 방법은 주로 2가지로 구분됨
  - `함수 선언식 (function declaration)`
  - `함수 표현식 (function expression)`

---

- **함수 선언식 (function declaration)**
  
  - 일반적인 프로그래밍 언어의 함수 정의 방식
    
    ```jsx
    function 함수명() {
        // do something
    }
    ```
    
    - 예시)
      
      ```jsx
      function add(num1, num2) {
          return num1 + num2
      }
      
      add(2, 7)    // 9
      ```

---

- **함수 표현식 (function expression)**
  
  - 표현식 내에서 함수를 정의하는 방식
  
  - 함수 표현식은 함수의 이름을 생략한 익명 함수로 정의 가능
    
    ```jsx
    변수키워드 함수명 = function () {
        // do something
    }
    ```
    
    - 예시)
      
      ```jsx
      const sub = function (num1, num2) {
          return num1 - num2
      }
      
      sub(7, 2)   // 5
      ```
  
  - 표현식에서 함수 이름을 명시하는 것도 가능
    
    - 다만 이 경우 함수 이름은 호출에 사용되지 못하고 디버깅 용도로 사용됨
    
    ```jsx
    const mySub = function namedSub(num1, num2) {
        return num1 - num2
    }
    
    mySub(1, 2)    // -1
    namedSub(1, 2) // ReferenceError : namedSub is not defined
    ```

---

- 기본 인자 (Default arguments)
  
  - 인자 작성 시 ‘=’ 문자 뒤 기본 인자 선언 가능
  
  ```jsx
  const greetig = function (name = 'Anonymous') {
      return `Hi ${name}`
  }
  
  greeting()      // Hi Anonymous
  ```

---

- 매개변수와 인자의 개수 불일치 허용
  
  - 매개변수보다 인자의 개수가 많을 경우
    
    ```jsx
    const noArgs = function () {
        return 0
    }
    
    noArgs(1, 2, 3)       // 0
    
    const twoArgs = function (arg1, arg2) {
        return [arg1, arg2]
    }
    
    twoArgs(1, 2, 3)      // [1, 2]
    ```
  
  - 매개변수보다 인자의 개수가 적을 경우
    
    ```jsx
    const threeArgs = function (arg1, arg2, arg3) {
        return [arg1, arg2, arg3]
    }
    
    threeArgs()       // [undefined, undefined, undefined]
    threeArgs(1)      // [1, undefined, undefined]
    threeArgs(1, 2)   // [1, 2, undefined]
    ```

- Spread syntax ( … )
  
  - 전개 구문
  
  - 전개 구문을 사용하면 배열이나 문자열과 같이 반복 가능한 객체를 배열의 경우는 요소, 함수의 경우는 인자로 확장할 수 있음
    
    1. 배열과의 사용 ( 배열 복사 )
       
       ```jsx
       let parts = ['shoulders', 'knees']
       let lyrics = ['head', ...parts, 'and', 'toes']
       // ['head', 'shoulders', 'knees', 'and', 'toes']
       ```
    
    2. 함수와의 사용 (`Rest parameters`)
       
       - 정해지지 않은 수의 매개변수를 배열로 받을 수 있음
       
       ```jsx
       function func(a, b, ...theArgs) {
        //
       }
       ```
       
       ```jsx
       const restOpr = function (arg1, arg2, ...restArgs) {
          return [arg1, arg2, restArgs]
       }
       restOpr(1, 2, 3, 4, 5)    // [1, 2, [3, 4, 5]]
       restOpr(1, 2)             // [1, 2, []]
       ```

---

### 선언식과 표현식

- 함수의 타입
  
  - 선언식 함수와 표현식 함수 모두 타입은 function 으로 동일
  
  ```jsx
  // 함수 표현식
  const add = function (args) { }
  
  // 함수 선언식
  function sub(args) { }
  
  console.log(typeof add)   // function
  console.log(typeof sub)   // function
  ```

- 호이스팅 - 선언식
  
  - 함수 선언식으로 정의한 함수는 var로 정의한 변수처럼 호이스팅이 발생
  - 즉, 함수 호출 이후에 선언해도 동작
  
  ```jsx
  add(2, 7)     // 9
  
  function add (num1, num2) {
      return num1 + num2
  }
  ```

- 호이스팅 - 표현식
  
  - 함수 표현식으로 선언한 함수는 함수 정의 전에 호출 시 에러 발생
  - 함수 표현식으로 정의된 함수는 변수로 평가되어 변수의 scope 규칙을 따름
  
  ```jsx
  sub(7, 2) // Uncaught ReferenceError : Cannot access 'sub' before initialization
  
  const sub = function (num1, num2) {
      return num1 - num2
  }
  ```

- 선언식과 표현식 정리
  
  |     | 선언식 (declaration)               | 표현식 (expression)                |
  | --- | ------------------------------- | ------------------------------- |
  | 공통점 | 데이터 타입, 함수 구성 요소 (이름, 매개변수, 바디) | 데이터 타입, 함수 구성 요소 (이름, 매개변수, 바디) |
  | 차이점 | 익명 함수 불가능, 호이스팅 있음              | 익명 함수 가능, 호이스팅 없음               |
  | 비고  |                                 | Airbnb Style Guide 권장 방식        |

---

### Arrow Function

- 화살표 함수 (Arrow Function)
  
  - 함수를 비교적 간결하게 정의할 수 있는 문법
  
  - function 키워드와 중괄호를 이용한 구문을 짧게 사용하기 위해 탄생
    
    1. `function` 키워드 생략 가능
    2. 함수의 매개변수가 하나뿐이라면 매개변수의 `()` 생략 가능
    3. 함수의 내용이 한 줄이라면 `{}` 와 `return` 도 생략 가능
  
  - 화살표 함수는 항상 익명 함수
    
    - 따라서 함수 표현식에서만 사용 가능
  
  - 화살표 함수 예시
    
    ```jsx
    const arrow1 = function (name) {
        return `hello, ${name}`
    }
    
    // 1. function  키워드 삭제
    const arrow2 = (name) => { return `hello, ${name}` }
    
    // 2. 인자가 1개일 경우에만 () 생략 가능
    const arrow3 = name => { return `hello, ${name}` }
    
    // 3. 함수 바디가 return을 포함한 표현식 1개일 경우에 {}, return 삭제 가능
    const arrow4 = name => `hello, ${name}`
    ```
    
    - 명확성과 일관성을 위해 항상 인자 주위에는 괄호 ( ) 를 포함하는 것을 권장
  
  - 화살표 함수 응용
    
    ```jsx
    // 1. 인자가 없다면? () or _로 표시 가능
    let noArgs = ()   => 'No args'
    noArgs = _        => 'No args'
    
    // 2-1. **object를 return** 한다면
    let returnObject = () => { return { key: 'value' } }  // return 을 명시적으로 적어줌
    
    // 2-2. return을 적지 않으려면 괄호를 붙여야 함
    returnObject = () => ({ key: 'value' })
    ```

---

- 즉시 실행 함수(IIFE, Immediately Invoked Function Expression)
  
  - 선언과 동시에 실행되는 함수
  - 함수의 선언 끝에 ( ) 를 추가하여 선언되자마자 실행하는 형태
  - ( ) 에 값을 넣어 인자로 넘겨줄 수 있음
  - 즉시 실행 함수는 선언과 동시에 실행되기 때문에 같은 함수를 다시 호출할 수 없음
  - 이러한 특징을 살려 초기화 부분에 많이 사용
  - 일회성 함수이므로 익명함수로 사용하는 것이 일반적
  
  ```jsx
  (function(num) { return num ** 3 })(2)     // 8
  
  (num => num ** 3)(2)                       // 8
  ```

---

### Array와 Object

- 개요
  - JavaScript의 데이터 타입 중 참조 타입(reference)에 해당하는 타입은 **Array**와 **Object**이며, 객체라고도 말함
  - 객체는 속성들의 모음(collection)

---

### 배열 (Array)

- 키와 속성들을 담고 있는 참조 타입의 객체
- 순서를 보장하는 특징이 있음
- 주로 대괄호([ ])를 이용하여 생성하고, 0을 포함한 양의 정수 인덱스로 특정 값에 접근 가능
- 배열의 길이는 array.length 형태로 접근 가능
  - 참고) 배열의 바지막 원소는 array.length -1 로 접근

```jsx
const numbers = [1, 2, 3, 4, 5]

console.log(numbers[0])      // 1
console.log(numbers[-1])     // undefined
console.log(numbers.length)  // 5
```

```jsx
const numbers = [1, 2, 3, 4, 5]

console.log(numbers[numbers.length - 1])   // 5
console.log(numbers[numbers.length - 2])   // 4
console.log(numbers[numbers.length - 3])   // 3
console.log(numbers[numbers.length - 4])   // 2
console.log(numbers[numbers.length - 5])   // 1
```

---

### 배열 메서드 기초

| 메서드             | 설명                           | 비고              |
| --------------- | ---------------------------- | --------------- |
| reverse         | 원본 배열의 요소들의 순서를 반대로 정렬       |                 |
| push & pop      | 배열의 가장 뒤에 요소를 추가 또는 제거       |                 |
| unshift & shift | 배열의 가장 앞에 요소를 추가 또는 제거       |                 |
| includes        | 배열에 특정 값이 존재하는지 판별 후 참/거짓 반환 |                 |
| indexOf         | 배열에 특정 값이 존재하는지 판별 후 인덱스 반환  | 요소가 없을 경우 -1 반환 |
| join            | 배열의 모든 요소를 구분자를 이용하여 연결      | 구분자 생략 시 쉼표 기준  |

- `array.reverse()`
  
  - 원본 배열 요소들의 순서를 반대로 정렬
  
  ```jsx
  const numbers = [1, 2, 3, 4, 5]
  numbers.reverse()
  console.log(numbers)      // [5, 4, 3, 2, 1]
  ```

- `array.push()`
  
  - 배열의 가장 뒤에 요소 추가

- `array.pop()`
  
  - 배열의 마지막 요소 제거
  
  ```jsx
  const numbers = [1, 2, 3, 4, 5]
  
  numbers.push(100)
  console.log(numbers)   // [1, 2, 3, 4, 5, 100]
  
  numbers.pop()
  console.log(numbers)   // [1, 2, 3, 4, 5]
  ```

- `array.includes(value)`
  
  - 배열에 특정 값(value)이 존재하는지 판별 후 true 또는 false 반환
  
  ```jsx
  const numbers = [1, 2, 3, 4, 5]
  
  console.log(numbers.includes(1))      // true
  console.log(numbers.includes(100))    // false
  ```

- `array.indexOf(value)`
  
  - 배열에 특정 값이 존재하는지 확인 후 가장 첫 번째로 찾은 요소의 인덱스 반환
  - 만약 해당 값이 없을 경우 -1 반환
  
  ```jsx
  const numbers = [1, 2, 3, 4, 5]
  let result
  
  result = numbers.indexOf(3)      // 2
  console.log(result)
  
  result = numbers.indexOf(100)    // -1
  console.log(result)
  ```

- `array.join([separator])`
  
  - 배열의 모든 요소를 연결하여 반환
  - separator(구분자)는 선택적으로 지정 가능하며, 생략 시 쉼표를 기본값으로 사용
  
  ```jsx
  const numbers = [1, 2, 3, 4, 5]
  let result
  
  result = numbers.join()     // 1, 2, 3, 4, 5
  console.log(result)
  
  result = numbers.join('')   // 12345
  console.log(result)
  
  result = numbers.join(' ')  // 1 2 3 4 5
  console.log(result)
  
  result = numbers.join('-')  // 1-2-3-4-5
  console.log(result)
  ```

---

### 배열 메서드 심화

- Array Helper Methods
  
  - 배열을 순회하며 특정 로직을 수행하는 메서드
  - 메소드 호출 시 인자로 `callback 함수` 를 받는 것이 특징
    - `callback 함수 : 어떤 함수의 내부에서 실행될 목적으로, 인자로 넘겨받는 함수`
  
  ---
  
  - `forEach`
    
    ```jsx
    array.forEach((element, index, array) => {
        // do something
    })
    ```
    
    - `array.forEach(callback(element[, index[,array]]))`
    - 인자로 주어지는 함수(콜백 함수)를 배열의 각 요소에 대해 한 번씩 실행
      - 콜백 함수는 3가지 매개변수로 구성
        1. element : 배열의 요소
        2. index : 배열 요소의 인덱스
        3. array : 배열 자체
      - **반환값(return) 없음**
    
    ```jsx
    // 1. 일단 사용해보기
    
    const colors = ['red', 'blue', 'green']
    
    printFunc = function (color) {
        console.log(color)
    }
    
    colors.forEach(printFunc)
    
    // red
    // blue
    // green
    ```
    
    ```jsx
    // 2. 함수 정의를 인자로 넣어보기
    
    colors.forEach(function (color) {
        console.log(color)
    })
    ```
    
    ```jsx
    // 3. 화살표 함수 적용하기
    
    colors.forEach((color) => {
        return console.log(color)
    })
    ```
    
    ---
  
  - `map`
    
    ```jsx
    array.map((element, index, array) => {
        // do something
    })
    ```
    
    - `array.map(callback(element[, index[, array]]))`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
    - **콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환**
    - 기존 배열 전체를 다른 형태로 바꿀 때 유용
      - `forEach + return` 이라고 생각하기
    
    ```jsx
    // 1. 일단 사용해보기
    
    const numbers = [1, 2, 3]
    
    // 함수 정의 (표현식)
    const doubleFunc = function (number) {
        return number * 2
    }
    
    // 함수를 다른 함수의 인자로 넣기 (콜백 함수)
    const doubleNumbers = numbers.map(doubleFunc)
    console.log(doubleNumbers)   // [2, 4, 6]
    ```
    
    ```jsx
    // 2. 함수 정의를 인자로 넣어보기
    
    const doubleNumbers = numbers.map(function (number) {
        return number * 2
    })
    console.log(doubleNumbers)   // [2, 4, 6]
    ```
    
    ```jsx
    // 3. 화살표 함수 적용하기
    
    const doubleNumbers = numbers.map((number) => {
        return number * 2
    })
    console.log(doubleNumbers)   // [2, 4, 6]
    ```
    
    ---
  
  - `filter`
    
    ```jsx
    array.filter((element, index, array) => {
        // do something
    })
    ```
    
    - `array.filter(callback(element[, index[, array]]))`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
    - **콜백 함수의 반환 값이 true인 요소들만 모아서 새로운 배열 반환**
    - 기존 배열의 요소들을 필터링할 때 유용
    
    ```jsx
    // 1. 일단 사용해보기
    
    const products = [
        { name: 'cucumber', type: 'vegetable' },
        { name: 'banana', type: 'fruit' },
        { name: 'carrot', type: 'vegetable' },
        { name: 'apple', type: 'fruit' },
    ]
    
    // 함수 정의하고
    const fruitFilter = function (product) {
        return product.type === 'fruit'
    }
    
    // 콜백으로 넘기고
    const fruits = products.filter(fruitFilter)
    
    console.log(fruits)
    // [{ name: 'banana', type: 'fruit' }, { name: 'apple', type: 'fruit' } ]
    ```
    
    ```jsx
    // 2. 함수 정의를 인자로 넣어보기
    
    const fruits = products.filter(function (product) {
        return product.type === 'fruit'
    })
    ```
    
    ```jsx
    // 3. 화살표 함수 적용하기
    
    const fruits = products.filter((product) => {
        return product.type === 'fruit'
    })
    ```
    
    ---
  
  - `reduce`
    
    ```jsx
    array.reduce((acc, element, index, array) => {
        // do something
    }, initalValue)
    ```
    
    - `array.reduce(callback(acc, element, [index[, array]])[, initialValue])`
    - 인자로 주어지는 함수(콜백 함수)를 배열의 각 요소에 대해 한 번씩 실행해서, 하나의 결과 값을 반환
    - 즉, 배열을 하나의 값으로 계산하는 동작이 필요할 때 사용(총합, 평균 등)
    - map, filter 등 여러 배열 메서드 동작을 대부분 대체할 수 있음
    - reduce 메서드의 주요 매개변수
      - acc
        - 이전 callback 함수의 반환 값이 누적되는 변수
      - initialValue (optional)
        - 최초 callback 함수 호출 시 acc에 할당되는 값, default 값은 배열의 첫 번째 값
    - reduce의 첫번째 매개변수인 콜백함수의 첫번째 매개변수(acc)는 누적된 값(전 단계까지의 결과)
    - reduce의 두번째 매개변수인 initialValue는 누적될 값의 초기값, 지정하지 않을 시 첫번째 요소의 값이 됨
    - `빈 배열의 경우 initialValue를 제공하지 않으면 에러 발생`
    
    ```jsx
    const tests = [90, 90, 80, 77]
    
    // 총합
    const sum = tests.reduce(function (total, x) {
        return total + x
    }, 0)         // 여기서 0 생략 가능
    
    // 화살표 함수
    const sum = tests.reduce((total, x) => total + x, 0)
    
    // 평균
    const sum = tests.reduce((total, x) => total + x, 0) / tests.length
    ```
    
    - reduce 동작 방식
      
      ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4804e0ff-eab8-4897-a158-c8896cb86a20/Untitled.png)
    
    ---

- `find`
  
  ```jsx
  array.find((element, index, array) => {
      // do something
  }
  ```
  
  - `array.find(callback(element[, index[, array]]))`
  - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
  - 콜백 함수의 반환 값이 true면, 조건을 만족하는 첫번째 요소를 반환
  - 찾는 값이 배열에 없으면 undefined 반환
  
  ```jsx
  const avengers = [
      { name: 'Tony Stark', age: 45 },
    { name: 'Steve Rogers', age: 32 },
      { name: 'Thor', age: 40 }
  ]
  
  const avenger = avengers.find(function (avenger) {
      return avenger.name === 'Tony Stark'
  })
  
  // 화살표 함수 적용
  const avenger = avengers.find((avenger) => {
      return avenger.name === 'Tony Stark'
  })
  ```
  
  ---

- `some`
  
  ```jsx
  array.some((element, index, array) => {
      // do something
  }
  ```
  
  - `array.some(callback(element[, index[, array]]))`
  - 배열의 요소 중 하나라도 주어진 판별 함수를 통과하면 true 반환
  - 모든 요소가 통과하지 못하면 거짓 반환
  - 빈 배열은 항상 false 반환
  
  ```jsx
  const arr = [1, 2, 3, 4, 5]
  
  const result = arr.some((elem) => {
      return elem % 2 === 0
  })
  //true
  ```
  
  ---

- `every`
  
  ```jsx
  array.every((element, index, array) => {
      // do something
  })
  ```
  
  - `array.every(callback(element[, index[, array]]))`
  - 배열의 모든 요소가 주어진 판별 함수를 통과하면 true 반환
  - 하나의 요소라도 통과하지 못하면 false 반환
  - 빈 배열은 항상 true 반환
  
  ```jsx
  const arr = [1, 2, 3, 4, 5]
  
  const result = arr.every((elem) => {
      return elem % 2 === 0
  })
  //false
  ```
  
  ---

- 배열 순회 비교
  
  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ebd95bdb-3a8c-4dda-b79f-8ae81a98b97b/Untitled.png)

---

### 객체 (Object)

- 개요
  
  - 객체는 속성(property)의 집합이며
  - 중괄호 내부에 key와 value의 쌍으로 표현
  - key
    - 문자열 타입만 가능
    - key 이름에 띄어쓰기 등의 구분자가 있으면 따옴표로 묶어서 표현
  - value
    - 모든 타입(함수 포함) 가능
  - 객체 요소 접근
    - 점(.) 또는 대괄호([ ])로 가능
    - key 이름에 띄어쓰기 같은 구분자가 있으면 대괄호 접근만 가능

- 예시
  
  ```jsx
  const me = {
      name: 'jack',
      phoneNumber: '01012345678',
      'samsung products': {
          buds: 'Galaxy Buds pro',
          galaxy: 'Galaxy s99'
      },
  }
  
  console.log(me.name)
  console.log(me['name'])
  console.log(me['samsung products'])
  console.log(me.samsung products])    // 불가능
  console.log(me['samsung products'].buds)
  ```

- 객체 관련 ES6 문법 익히기
  
  1. 속성명 축약
  2. 메서드명 축약
  3. 계산된 속성명 사용
  4. 구조 분해 할당
  5. 객체 전개 구문(Spread Operator)
1. 속성명 축약
   
   - 객체를 정의할 때 key와 할당하는 변수의 이름이 같으면 예시와 같이 축약 가능
   
   ```jsx
   // ES5
   var books = ['Learning JavaScript', 'Learning Python']
   var magazines = ['Vogue', 'Science']
   
   var bookShop = {
      books: books,
      magazines: magazines,
   }
   console.log(bookShop)
   
   /*
   {
      books: ['Learning JavaScript', 'Learning Python'],
      magazines: ['Vogue', 'Science']
   }
   */
   
   // ES6+
   const books = ['Learning JavaScript', 'Learning Python']
   const magazines = ['Vogue', 'Science']
   
   const bookShop = {
      books,
      magazines,
   }
   console.log(bookShop)
   
   /*
   {
      books: ['Learning JavaScript', 'Learning Python'],
      magazines: ['Vogue', 'Science']
   }
   */
   ```

2. 메서드명 축약
   
   - 메서드 선언 시 function 키워드 생략
   
   ```jsx
   // ES5
   var obj = {
      greeting: function () {
          console.log('Hi~')
      }
   }
   
   obj.greeting()     // Hi~
   ```
   
   ```jsx
   // ES6+
   const obj = {
      greeting() {
          console.log('Hi~')
      }
   }
   
   obj.greeting()     // Hi~
   ```

3. 계산된 속성
   
   - 객체를 정의할 때 key의 이름을 표현식을 이용하여 동적으로 생성 가능
   
   ```jsx
   const key = 'country'
   const value = ['한국', '미국', '일본', '중국']
   
   const myObj = {
      [key]: value,
   }
   
   console.log(myObj)         // { country: ['한국', '미국', '일본', '중국'] }
   console.log(myObj.country) // ['한국', '미국', '일본', '중국']
   ```

4. 구조 분해 할당
   
   - 배열 또는 객체를 분해하여 속성을 변수에 쉽게 할당할 수 있는 문법
   
   ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/288dfb06-6038-4891-b9c6-c93f6286df69/Untitled.png)

5. Spread syntax (…)
   
   - 배열과 마찬가지로 전개구문을 사용해 객체 내부에서 객체 전개 가능
   
   - 얕은 복사에 활용 가능
     
     ```jsx
     const obj = {b: 2, c: 3, d: 4}
     const newObj = {a: 1, ...obj, e: 5}
     
     console.log(newObj)   // {a: 1, b: 2, c: 3, d: 4, e: 5}
     ```
- JSON
  
  - JavaScript Object Notation
  - Key - Value 형태로 이루어진 자료 표기법
  - JavaScript의 Object와 유사한 구조를 가지고 있지만 Object는 그 자체로 타입이고, JSON은 형식이 있는 “문자열”
  - 즉, JSON을 Object로 사용하기 위해서는 변환 작업이 필요
  
  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/565efc87-94e4-40a1-971f-b7e4607f750a/Untitled.png)

- 참고) 배열은 객체다
  
  - 배열은 키와 속성들을 담고 있는 참조 타입의 객체
  - 배열은 인덱스를 키로 가지며 length 프로퍼티를 갖는 특수한 객체
  
  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2af22412-22af-4e3d-9317-9d5e32e60ad7/Untitled.png)

---

# DOM

### 개요

- 브라우저에서의 JavaScript
  - JavaScript는 웹 페이지에서 다양한 기능을 구현하는 스크립트 언어
  - 정적인 정보만 보여주던 웹 페이지를 데이터가 주기적으로 갱신되거나, 사용자와 상호 작용을 하거나, 애니메이션 등이 동작하게 하는 것을 가능하게 함
  - 참고) 스크립트 언어 (Script Language)
    - 기존에 존재하는 응용 소프트웨어를 제어하는 컴퓨터 프로그래밍 언어

### 웹 페이지에서의 JavaScript

- JavaScript는 프로그래밍 언어로서의 역할도 가능하지만 클라이언트 사이드 JavaScript 언어 위에 올라가 있는 기능들은 더 다양함
- API라고 부르는 이 기능들은 JavaScript 코드에서 사용할 수 있는 것들을 더 무궁무진하게 만들어 줌
- 이 API는 일반적으로 2개의 범주로 분류할 수 있음
  1. Browser APIs
  2. Third party APIs
     - 브라우저에 탑재되지 않은 API
     - 웹에서 직접 코드와 정보를 찾아야 함
     - Google map API, kakao login API 등

---

### DOM

- Browser APIs
  - 웹 브라우저에 내장된 API로, 웹 브라우저가 현재 컴퓨터 환경에 관한 데이터를 제공하거나, 오디오를 재생하는 등 여러 가지 유용하고 복잡한 일을 수행할 수 있게 함
  - JavaScript로 Browser API 들을 사용해서 여러 가지 기능을 사용할 수 있음
  - 종류
    - DOM
    - Geolocaton API
    - WebGL
    - 등등…
- 브라우저가 웹 페이지를 불러오는 과정
  - 웹 페이지를 브라우저로 불러오면, 브라우저는 코드(HTML, CSS, JavaScript)를 실행 환경(브라우저 탭)에서 실행
  - JavaScript는 **DOM API**를 통해 HTML과 CSS를 동적으로 수정, 사용자 인터페이스를 업데이트하는 일에 가장 많이 쓰임
- DOM
  - 문서 객체 모델 (Document Object Model)
  - 문서의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공
    - 문서 구조, 스타일, 내용 등을 쉽게 변경할 수 있게 도움
    - HTML 콘텐츠를 추가, 제거, 변경하고, 동적으로 페이지에 스타일을 추가하는 등 HTML/CSS를 조작할 수 있음
  - HTML 문서를 구조화하여 각 요소를 객체 (object) 로 취급
  - 단순한 속성 접근, 메서드 활용 뿐만 아니라 프로그래밍 언어적 특성을 활용한 조작이 가능함
  - DOM은 문서를 논리 트리로 표현
  - DOM 메서드를 사용하면 프로그래밍적으로 트리에 접근 가능, 이를 통해 문서의 구조, 스타일, 컨텐츠를 변경할 수 있음
  - 웹 페이지는 일종의 문서(document)
  - 이 문서는 웹 브라우저를 통해 그 내용이 해석되어 웹 브라우저 화면에 나타나거나 HTML 코드 자체로 나타나기도 함
  - DOM은 동일한 문서를 표현하고, 저장하고, 조작하는 방법을 제공
  - DOM은 웹 페이지의 객체 지향 표현이며, JavaScript와 같은 스크립트 언어를 이용해 DOM을 수정할 수 있음
- DOM에 접근하기
  - DOM을 사용하기 위해 특별히 해야 할 일은 없음
  - 모든 웹 브라우저는 스크립트 언어가 손쉽게 웹 페이지의 요소에 접근할 수 있도록 만들기 위해 DOM 구조를 항상 사용
  - 우리는 “DOM의 주요 객체”들을 활용하여 문서를 조작하거나 특정 요소들을 얻을 수 있음
- DOM의 주요 객체
  - `window`
  - `document`
  - navigator, location, history, screen 등
- `window` object
  - DOM 을 표현하는 창
  - 가장 최상위 객체 (작성 시 생략 가능)
  - 탭 기능이 있는 브라우저에서는 각각의 탭을 각각의 window 객체로 나타냄
- `document` object
  - 브라우저가 불러온 웹 페이지
  - 페이지 컨텐츠의 진입점 역할을 하며, <body>등과 같은 수많은 다른 요소들을 포함하고 있음
- [참고] 파싱 (Parsing)
  - 구문 분석, 해석
  - 브라우저가 문자열을 해석하여 DOM Tree로 만드는 과정

---

### DOM 조작

- 개요
  
  - Document가 제공하는 기능을 사용해 웹 페이지 문서 조작하기
  - DOM 조작 순서
    1. 선택 (Select)
    2. 조작 (Manipulation)
       - 생성, 추가, 삭제 등

- 선택 관련 메서드
  
  - `document.querySelector(selector)`
    - 제공한 선택자와 일치하는 element 한 개 선택
    - 제공한 CSS selector를 만족하는 첫 번째 element 객체를 반환 (없다면 null 반환)
  - `document.querySelectorAll(selector)`
    - 제공한 선택자와 일치하는 여러 element를 선택
    - 매칭할 하나 이상의 selector를 포함하는 유효한 CSS selector를 인자(문자열)로 받음
    - 제공한 CSS selector를 만족하는 NodeList를 반환

- [참고] NodeList
  
  - index로만 각 항목에 접근 가능
  - 배열의 forEach 메서드 및 다양한 배열 메서드 사용 가능
  - `querySelectorAll()` 에 의해 반환되는 NodeList는 DOM의 변경사항을 실시간으로 반영하지 않음

- 조작 관련 메서드 (생성)
  
  - `document.createElement(tagName)`
    - 작성한 tagName의 HTML 요소를 생성하여 반환

- 조작 관련 메서드 (입력)
  
  - `Node.innerText`
    - Node 객체와 그 자손의 텍스트 컨텐츠 (DOMString) 를 표현
      - 해당 요소 내부의 raw text
    - 사람이 읽을 수 있는 요소만 남김
    - 즉, 줄 바꿈을 인식하고 숨겨진 내용을 무시하는 등 최종적으로 스타일링이 적용된 모습으로 표현됨

- 조작 관련 메서드 (추가)
  
  - `Node.appendChild()`
    - 한 Node를 특정 부모 Node의 자식 NodeList 중 마지막 자식으로 삽입
    - 한번에 오직 하나의 Node만 추가할 수 있음
    - 추가된 Node 객체를 반환
    - 만약 주어진 Node가 이미 문서에 존재하는 다른 Node를 참조한다면 현재 위치에서 새로운 위치로 이동

- 조작 관련 메서드 (삭제)
  
  - `Node.removeChild()`
    - DOM에서 자식 Node를 제거
    - 제거된 Node를 반환

- ex)
  
  ```jsx
  // h1 요소(element)를 만들고
      const title = document.createElement('h1')
  
      // 텍스트를 추가
      title.innerText = '이것이 이너텍스트'
  
      // 선택자로 div 태그를 가져와서
      const div = document.querySelector('div')
  
      // div 태그의 자식 요소로 추가
      div.appendChild(title)
  
      // div의 h1 요소 삭제
      div.removeChild(title)
  ```

- 조작 관련 메서드 (속성 조회 및 설정)
  
  - `Element.getAttribute(attributeName)`
    - 해당 요소의 지정된 값(문자열)을 반환
    - 인자(attributeName)는 값을 얻고자 하는 속성의 이름
  - `Element.setAttribute(name, value)`
    - 지정된 요소의 값을 설정
    - 속성이 이미 존재하면 값을 갱신, 존재하지 않으면 지정된 이름과 값으로 새 속성을 추가

---

### DOM 조작 정리

1. 선택한다
   - `querySelector()`
   - `querySelectorAll()`
2. 조작한다
   - `innerText`
   - `setAttribute()`
   - `getAttribute()`
   - `createElement()`
   - `appendChild()`
   - `...`

---

## Event

- 개요
  - `Event` 란 프로그래밍하고 있는 시스템에서 일어나는 사건(action) 혹은 발생(occurence)으로, 각 이벤트에 대해 조작할 수 있도록 특정 시점을 시스템이 알려주는 것
    - 예를 들어, 사용자가 웹 페이지의 버튼을 클릭한다면 클릭에 대해 이벤트가 발생하고 우리는 이벤트를 통해 클릭이라는 사건에 대한 결과를 받거나, 조작을 할 수 있음
  - 클릭 말고도 웹에서는 각양각색의 Event가 존재
    - 키보드 키 입력, 브라우저 닫기, 데이터 제출, 텍스트 복사 등

---

- Event object
  - 네트워크 활동이나 사용자와의 상호작용 같은 사건의 발생을 알리기 위한 객체
  - Event 발생
    - 마우스를 클릭하거나 키보드를 누르는 등 사용자 행동으로 발생할 수도 있고
    - 특정 메서드를 호출하여 프로그래밍적으로도 만들어 낼 수 있음
  - DOM 요소는 Event를 받고 (`"수신"`)
  - 받은 Event를 `"처리"` 할 수 있음
    - Event 처리는 주로 `addEventListener()` 라는 Event 처리기(Event handler)를 다양한 html 요소에 `"부착"` 해서 처리함

---

### Event handler - `addEventListener()`

- **대상**에 **특정 Event**가 발생하면, **할 일**을 등록하자
  - **EventTarget**.addEventListener(**type**, **listener**)
- `EventTarget.addEventListener(type, listener[, options])`
  - 지정한 Event가 대상에 전달될 때마다 호출할 함수를 설정
  - Event를 지원하는 모든 객체(Element, Document, Window 등)를 대상(EventTarget)으로 지정 가능
- `EventTarget.addEventListener(**type**, listener[, options])`
  - type
    - 반응할 Event 유형을 나타내는 대소문자 구분 문자열
    - 대표 이벤트
      - input, click, submit, …
- `EventTarget.addEventListener(type, **listener**[, options])`
  - listener
    - 지정된 타입의 Event를 수신할 객체
    - JavaScript function 객체 (콜백 함수)여야 함
    - 콜백 함수는 발생한 Event의 데이터를 가진 Event 객체를 유일한 매개변수로 받음
- `addEventListener` 정리
  - ~ 하면 ~ 한다.
    - 클릭하면, 경고창을 띄운다…
    - 특정 Event가 발생하면, 할 일(콜백 함수)을 등록한다…

---

### Event 취소

- `event.preventDefault()`
  - 현재 Event의 기본 동작을 중단
  - HTML 요소의 기본 동작을 작동하지 않게 막음
  - HTML 요소의 기본 동작 예시
    - a 태그 : 클릭 시 특정 주소로 이동
    - form 태그 : form 데이터 전송

---

### [참고] lodash

- 모듈성, 성능 및 추가 기능을 제공하는 JavaScript 유틸리티 라이브러리
- array, object 등 자료구조를 다룰 때 사용하는 유용하고 간편한 유틸리티 함수들을 제공
- 함수 예시
  - reverse, sortBy, range, random …
- [https://lodash.com/](https://lodash.com/)

---

### this

- 어떠한 object를 가리키는 키워드
  - java에서의 this와 python에서으이 self는 인스턴스 자기자신을 가리킴
- JavaScript의 함수는 호출될 때 this를 암묵적으로 전달 받음
- JavaScript에서의 this는 일반적인 프로그래밍 언어에서의 this와 조금 다르게 동작
- JavaScript는 해당 `함수 호출 방식` 에 따라 this에 바인딩 되는 객체가 달라짐
- 즉, 함수를 선언할 때 this에 객체가 결정되는 것이 아니고, 함수를 호출할 때 `함수가 어떻게 호출 되었는지에 따라 동적으로 결정` 됨

### this INDEX

1. 전역 문맥에서의 this

2. 함수 문맥에서의 this
   
   - 단순 호출
   - Method (객체의 메서드로서)
   - Nested
- 전역 문맥에서의 this
  
  - 브라우저의 전역 객체인 window를 가리킴
    
    - 전역 객체는 모든 객체의 유일한 최상위 객체를 의미
    
    ```jsx
    console.log(this)            // window
    ```

- 함수 문맥에서의 this
  
  - 함수의 this 키워드는 다른 언어와 조금 다르게 동작
    
    - this의 값은 함수를 호출한 방법에 의해 결정됨
    - 함수 내부에서 this의 값은 함수를 호출한 방법에 의해 좌우됨
  1. `단순 호출`
     
     1. 전역 객체를 가리킴
     
     2. 전역은 브라우저에서는 window, Node.js는 global을 의미함
        
        ```jsx
        const myFunc = function () {
          console.log(this)
        }
        
        // 브라우저
        myFunc()    // window
        
        // Node.js
        myFunc()    // global
        ```
  
  2. `Method (Function in Object, 객체의 메서드로서)`
     
     1. 메서드로 선언하고 호출한다면, 객체의 메서드이므로 해당 객체가 바인딩
        
        ```jsx
        const myObj = {
          data: 1,
          myFunc() {
              console.log(this)      // myObj
              console.log(this.data) // 1
          }
        }
        
        myObj.myFunc()             // myObj
        ```
  
  3. `Nested (Function 키워드)`
     
     1. forEach의 콜백 함수에서의 this가 메서드의 객체를 가리키지 못하고 전역 객체 window를 가리킴
     2. 단순 호출 방식으로 사용되었기 때문
     3. 이를 해결하기 위해 등장한 함수 표현식이 바로 `화살표 함수`
     
     ```jsx
     const myObj = {
        numbers: [1],
        myFunc() {
            console.log(this)      // myObj
            this.numbers.forEach(function (number) {
                console.log(number)  // 1
                console.log(this)    // window
            })
        }
     }
     
     myObj.myFunc()
     ```
     
     - Nested (화살표 함수)
       
       - 이전에 일반 function 키워드와 달리 메서드의 객체를 잘 가리킴
       - 화살표 함수에서 this는 자신을 감싼 정적 범위
       - 자동으로 한 단계 상위의 scope의 context를 바인딩
       
       ```jsx
       const myObj = {
          numbers: [1],
          myFunc() {
              console.log(this)      // myObj
              this.numbers.forEach((number) => {
                  console.log(number)  // 1
                  console.log(this)    // myObj
              })
          }
       }
       
       myObj.myFunc()
       ```

---

### 화살표 함수

- 화살표 함수는 호출의 위치와 상관없이 상위 스코프를 가리킴
- Lexical scope
  - 함수를 어디서 호출하는지가 아니라 `어디에 선언` 하였는지에 따라 결정
  - Static scope라고도 하며 대부분의 프로그래밍 언어에서 따르는 방식
- 따라서 함수 내의 함수 상황에서 화살표 함수를 쓰는 것을 권장
- 하지만..
  - addEventListener에서의 콜백 함수는 특별하게 function 키워드의 경우 addEventListener를 호출한 대상을 뜻함 (`event.target`)
  - 반면 화살표 함수의 경우 상위 스코프를 지칭하기 때문에 window 객체가 바인딩 된다
- 결론
  - addEventListener의 콜백 함수는 function 키워드를 사용하기

```jsx
<body>
  <button id="function">function</button>
  <button id="arrow">arrow function</button>

  <script>
    const functionButton = document.querySelector('#function')
    const arrowButton = document.querySelector('#arrow')

    functionButton.addEventListener('click', function(event) {
      console.log(this);      // <button id="function">function</button>
    })

    arrowButton.addEventListener('click', event => {
      console.log(this);      // window
    })
  </script>
</body>
```

---

### this 정리

- 이렇게 this가 런타임에 결정되면 장점도 있고 단점도 있음
- 함수(메서드)를 하나만 만들어 여러 객체에서 재사용할 수 있다는 것은 장점이지만, 이런 유연함이 실수로 이어질 수 있다는 것은 단점

---

### Single Thread 언어, JavaScript

- 응답이 먼저 오는 순서대로 처리하지 말고, 아예 여러 작업을 동시에 처리하면 되지 않을까?
- JavaScript는 한 번에 하나의 일만 수행하는 Single Thread 언어로 동시에 여러 작업을 처리할 수 없음
  - Thread란?
    - 작업을 처리할 때 실제로 작업을 수행하는 주체로, multi-thread라면 업무를 수행할 수 있는 주체가 여러 개라는 의미
- 즉, JavaScript는 하나의 작업을 요청한 순서대로 처리할 수 밖에 없다!
- Single Thread인 JavaScript가 어떻게 비동기 처리를 할 수 있을까?
  - JavaScript Runtime

---

### JavaScript Runtime

- Runtime
  - 특정 언어가 동작할 수 있는 환경
- JavaScript에서 비동기와 관련한 작업은 브라우저 또는 Node 환경에서 처리
- 이 중에서 브라우저 환경에서의 비동기 동작은 크게 아래의 요소들로 구성됨
  1. JavaScript Engine의 `Call Stack`
  2. `Web API`
  3. `Task Queue`
  4. `Event Loop`

---

### 비동기 처리 동작 방식

- 브라우저 환경에서의 JavaScript의 비동기는 아래와 같이 처리된다.
  
  1. 모든 작업은 Call Stack(LIFO)으로 들어간 후 처리된다.
  2. 오래 걸리는 작업이 Call Stack으로 들어오면 Web API로 보내서 처리하도록 한다.
  3. Web API에서 처리가 끝난 작업들은 Task Queue(FIFO)에 순서대로 들어간다.
  4. Event Loop가 Call Stack이 비어 있는 것을 체크하고 Task Queue에서 가장 오래된 작업을 Call Stack으로 보낸다.
1. `Call Stack`
   
   1. 요청이 들어올 때마다 순차적으로 처리하는 Stack(LIFO). 기본적인 JavaScript의 Single Thread 작업 처리

2. `Web API`
   
   1. JavaScript 엔진이 아닌 브라우저에서 제공하는 runtime 환경으로 시간이 소요되는 작업을 처리 (setTimeout, DOM event, AJAX 요청 등)

3. `Task Queue`
   
   1. 비동기 처리된 Callback 함수가 대기하는 Queue(FIFO)

4. `Event Loop`
   
   1. Call Stack과 Task Queue를 지속적으로 모니터링
   2. Call Stack이 비어 있는지 확인 후 비어 있다면 Task Queue에서 대기 중인 오래된 작업을 Call Stack 으로 Push
- 정리
  - JavaScript는 한 번에 하나의 작업을 수행하는 Single Thread 언어로 동기적 처리를 하지만, 브라우저 환경에서는 Web API에서 처리된 작업이 지속적으로 Task Queue를 거쳐 Event Loop에 의해 Call Stack에 들어와 순차적으로 실행됨으로써 비동기 작업이 가능한 환경이 된다.

---

### Axios

- JavaScript의 HTTP 웹 통신을 위한 라이브러리

- node 환경은 npm을 이용해서 설치 후 사용할 수 있고,
  
    browser 환경은 CDN을 이용해서 사용할 수 있음

```jsx
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
<script>
    axios.get('요청할 URL')
        .then(성공하면 수행할 콜백함수)
        .catch(실패하면 수행할 콜백함수)
</script>
```

- get, post 등 여러 method 사용 가능

- `then` 을 이용해서 성공하면 수행할 로직을 작성

- `catch` 를 이용해서 실패하면 수행할 로직을 작성

- Axios 실습
  
  ```jsx
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
  </head>
  <body>
      <button>야옹</button>
  
      <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
  
      <script>
          console.log('고양이는 야옹');
          const catImageSearchURL = 'https://api.thecatapi.com/v1/images/search'
          const btn = document.querySelector('button')
  
          btn.addEventListener('click', function() {
              axios.get(catImageSearchURL)
                  .then((response) => {
                      imgElem = document.createElement('img')
                      imgElem.setAttribute('src', response.data[0].url)
                      document.body.appendChild(imgElem)
                  })
                  .catch((error) => {
                      console.log('실패햇다옹');
                  })
                  console.log('야옹야옹');
          })
      </script>
  
  </body>
  </html>
  ```

- 정리
  
  - axios는 비동기로 데이터 통신을 가능하게 하는 라이브러리
  - 같은 방식으로 Django REST API로 요청을 보내서 데이터를 받아온 후 처리할 수 있음

---

### Callback과 Promise

- 비동기 처리의 핵심은 Web API로 들어오는 순서가 아니라 `작업이 완료되는 순서에 따라 처리` 한다는 것!

- 개발자 입장에서 코드의 실행 순서가 불명확하다는 단점이 있음
  
  - 어떻게 해결할까?
    
      ⇒ `콜백 함수를 사용하자!!!`

---

### Callback Function (콜백 함수)

- `다른 함수의 인자로 전달되는 함수` 를 콜백 함수라고 한다.
- 비동기에만 사용되는 함수가 아니며 동기, 비동기 상관없이 사용 가능
- 시간이 걸리는 `비동기 작업이 완료된 후 실행할 작업을 명시하는 데 사용` 되는 콜백 함수를 비동기 콜백 (asynchronous callback) 이라 부름

```jsx
const btn = document.querySelector('button')
btn.addEventListener('click', () => {
    alert('Completed')
})
```

- 콜백 함수를 사용하는 이유
  - 명시적인 호출이 아닌 특정한 조건 혹은 행동에 의해 호출되도록 작성할 수 있음
  - “요청이 들어오면”, “이벤트가 발생하면”, “데이터를 받아오면” 등의 조건으로 이후 로직을 제어할 수 있음
  - `비동기 처리를 순차적으로 동작할 수 있게 함`
  - 비동기 처리를 위해선ㄴ 콜백 함수의 형태가 반드시 필요함
- 콜백 함수는 비동기 작업을 순차적으로 실행할 수 있게 하는 반드시 필요한 로직이지만, 콜백 지옥은 반드시 나타나는 문제
  - 코드의 가독성을 해침
  - 유지 보수가 어려움

---

### Promise (프로미스)

- Callback Hell 문제를 해결하기 위해 등장한 비동기 처리를 위한 객체
- “작업이 끝나면 실행시켜줄게”라는 약속(promise)
- `비동기 작업의 완료 또는 실패를 나타내는 객체`
- Promise 기반의 클라이언트가 바로 이전에 사용한 Axios 라이브러리
  - 성공에 대한 약속 `then()`
  - 실패에 대한 약속 `catch()`
- `then(callback)`
  - 요청한 작업이 성공하면 callback 실행
  - callback은 **이전 작업의 성공 결과**를 인자로 전달 받음
- `catch(callback)`
  - then()이 하나라도 실패하면 callback 실행
  - callback은 **이전 작업의 실패 객체**를 인자로 전달 받음
- then과 catch 모두 항상 promise 객체를 반환. 즉, 계속해서 chaining을 할 수 있음
- `axios로 처리한 비동기 로직이 항상 promise 객체를 반환`. 그래서 then을 계속 이어 나가면서 작성할 수 있었던 것

```jsx
// promise 방식

work1()
    .then((result1) => {
        // work2
        return result2
    })
    .then((result2) => {
        // work3
        return result3
    })
    .catch((error) => {
        // error handling
    })
```

- promise 방식은 비동기 처리를 위해 마치 일반적으로 위에서 아래로 적는 방식처럼 코드를 작성할 수 있음

---

### Promise가 보장하는 것 ( vs 비동기 콜백 )

- 비동기 콜백 작성 스타일과 달리 Promise가 보장하는 특징
1. callback 함수는 JavaScript의 Event Loop가 현재 실행 중인 Call Stack을 완료하기 이전에는 절대 호출되지 않음
   1. Promise callback 함수는 Event Queue에 배치되는 엄격한 순서로 호출됨
2. 비동기 작업이 성공하거나 실패한 뒤에 .then() 메서드를 이용하여 추가한 경우에도 1번과 똑같이 동작
3. .then() 을 여러 번 사용하여 여러 개의 callback 함수를 추가할 수 있음 (Chaining)
   1. 각각의 callback은 주어진 순서대로 하나하나 실행하게 됨
   2. Chaining은 Promise의 가장 뛰어난 장점

---

### AJAX

- 비동기 통신을 이용하여 화면 전체를 새로고침 하지 않아도 서버로 요청을 보내고, 데이터를 받아 화면의 일부분만 업데이트 가능
- 이러한 ‘비동기 통신 웹 개발 기술’을 Asynchronous Javascript And XML(AJAX) 라 함
- `AJAX의 특징`
  - 페이지 새로고침 없이 서버에 요청
  - 서버로부터 응답(데이터)를 받아 작업을 수행
- 이러한 비동기 웹 통신을 위한 라이브러리 중 하나가 Axios





---



### ES (ECMAScript)

- Ecma International이 ECMA-262 기술 규격에 따라 정의하고 있는 표준화된 스크립트 프로그래밍 언어
- `ES6` 는 2015년, `ES5` 는 2009년에 출시 (숫자는 버전을 의미함)

---

## ES6 문법 정리

### 1. let, const

- let
  - 블록스코프, 재할당 가능, 재선언 불가
  - 변수 선언 키워드
- const
  - 블록스코프, 재할당 불가, 재선언 불가
  - 상수 선언 키워드

### 2. 템플릿 리터럴

- ``(back tick) 으로 사용
- `${}` 형식을 통해 자바스크립트 표현식 사용 가능

```jsx
// ES5 문법으로 Hello, World! 출력하기
var str1 = ', ';
var str2 = 'World!';
var str3 = 'Hello' + str1 + str2;
```

```jsx
// ES6 문법으로 Hello, World! 출력하기
let str1 = ', ';
let str2 = 'World!';
let str3 = `Hello${str1} ${str2}`;
```

### 3. 객체 리터럴

**💥 객체**

- 객체는 JavaScript에서 데이터를 표현하는 방식 중 하나
- key, value 쌍으로 구성됨

```jsx
let example = {
    'name': '박시현',
    'age': 20
}

// 프로퍼티   : 'name': '박시현' 과 'age': 20
// 키 (key)   : 프로퍼티 명
// 값 (value) : 프로퍼티 값
```

- JavaScript는 prototype 기반 객체지향 언어로, 다양한 객체 생성 방법 지원
  
  - 객체 리터럴
  - Object 생성자 함수
  - 생성자 함수
  - Object.create 메서드
  - 클래스 (ES6)

- 객체 리터럴
  
  - 객체 생성 방식 중 가장 일반적이고 간단함
    
    - 컨텐츠를 그대로 대입하는 방법
  
  - 객체 리터럴 방식을 통해 Person이란 객체 생성해보면
    
    ```jsx
    let person = {
      name: ['Sihyun', 'Park'],
      age: 29,
      gender: 'male',
      interests: ['music', 'movie'],
      introduce: function() {
        console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old`);
      },
      greeting: function() {
        console.log(`Hi! I'm ${this.name[0]}.`);
      }
    };
    ```
    
    - 위 객체에서 `introduce`와 `greeting` 은 함수. 객체는 property로 일반 변수 뿐만 아니라 함수 또한 가질 수 있음
      - 이 함수를 `메서드` 라고 표현!! (메서드는 객체에 묶인 함수)

- 프로퍼티 접근
  
  - 선언한 프로퍼티에 접근할 수 있는 방법은 2가지
    
    1. 마침표 표기법
       - `person.name`, `person.age` 와 같이 접근
    2. 대괄호 표기법
       - `person['name']` , `person['age']` 와 같이 접근
       - 이 경우 ‘’(따옴표) 안에 감싸주지 않으면 name이란 변수의 값으로 인식하므로 꼭 감싸기
  
  - 메서드도 동일
    
    ```jsx
    person.introduce()
                // Sihyun Park is 29 years old.
    
    person.greeting()
                // Hi! I'm Sihyun.
    ```

- 프로퍼티 값 갱신
  
  - 이미 존재하는 property의 값을 수정하면 갱신됨
  
  ```jsx
  person.name = 'Gyuri'
  ```

- 프로퍼티 값 생성
  
  - 존재하지 않는 property의 값을 할당하면 프로퍼티가 동적으로 생성됨
  
  ```jsx
  person.address = 'Suwon' 
  ```

- 프로퍼티 값 삭제
  
  - 삭제하고자 하는 property를 delete 키워드 붙여 사용
  - 없는 property에 접근 시 에러 없이 무시됨
  
  ```jsx
  delete person.age
  ```

- 객체 리터럴 정리
  
  - 이전보다 훨씬 간결해진 코드로 객체 선언
  - 메소드에 :(콜론) 이나 function을 붙이지 않아도 됨
  - 함수명이 겹치는 경우 한 번만 사용 가능
  - 객체의 프로퍼티를 동적으로 생성하려면 객체 리터럴 밖에서 [text + 1]과 같이 선언했어야 했는데, ES6부터는 객체 안에서 바로 속성으로 사용 가능
  
  ```jsx
  const myFunc = function() {
      console.log('myFunc')
  }
  
  const text = 'TEXT'
  
  const obj = {
      inside() {
          console.log('객체 안에 바로 함수 선언')
      },
      myFunc,
      [text + 1]: '박시현'
  }
  
  obj.inside()  // 출력값 : 객체 안에 바로 함수 선언
  obj.myFunc()  // 출력값 : myFunc
  console.log(obj.TEXT1)   // 출력값 : 박시현
  ```

### 4. 화살표 함수

- 함수 표현식을 화살표 함수로 표현 가능
- 함수를 간결하게 나타낼 수 있게 되어 가독성 및 유지보수성 상승
- 함수의 본문(body)에 return만 있는 경우 화살표 함수는 return과 {}를 생략 가능(단, 같이 생략해야함)
- return 문에서 소괄호는 사용 가능

```jsx
// ES5
function plusFunc(a, b) {
    return a + b
}

// ES6
// 함수 표현식 (화살표 함수)
const plusFunc = (a, b) => {
    return a + b
}
// 함수 표현식 (화살표 함수, 생략형)
const plusFunc = (a, b) => a + b
```

### 5. 구조 분해 할당

- 객체나 배열에서 사용
- 값을 해체한 후 개별 값을 변수에 새로 할당하는 과정

```jsx
// 배열에서 사용
const arr = [1, 2, 3]
const [one, two, three] = arr

one // 1
two // 2
three // 3

////////////////////////////////////
// 객체에서 사용
const obj = {
    firstName: '시현',
    lastName: '박'
}

const { firstName, lastName } = obj
firstName // 시현
lastName // 박
```

### 6. Promise

- JavaScript에서는 비동기 처리를 기존에는 콜백 함수를 사용한 콜백 패턴으로 함
  - 이는 콜백지옥 발생시킴
- 이를 해결하기 위해 Promise 도입
- Promise 후속처리 메서드를 이용해 효율적 에러 처리 가능

### 7. Class

- JavaScript는 프로토타입 기반의 객체 지향 언어
- 클래스 기반의 객체 지향 프로그래밍 가능하도록 Class 키워드 도입
- JavaScript에서 Class는 내부적으로 프로토타입을 이용해 만들어짐
- 호이스팅이 `let` , `const` 키워드처럼 동작

### 8. String Method (includes, startsWith, endsWith)

- includes : 포함 여부
- startsWith : 시작하는지
- endsWith : 끝나는지
- boolean 타입을 return 함

```jsx
const str = 'Hello World Sihyun'
str.includes("Sihyun")   // true
str.startsWith("Hello")  // true
str.endsWith("yun")      // true
```

### 9. Multi-line String

- 과거에 문자열이 라인을 넘어간다면 `\\n` 과 `덧셈 연산자` 필요했음

```jsx
// ES5
var str = 'asdhasfhfsahsfhfshasfhsfahsfahsfahasfh.\\n' + 
'mxmxmxmxmxmxmxmmxmxmxmxmxmmxmxmxmxmxm.\\n'
```

- 백틱을 사용하게 되며 여러 줄의 문자열 관리가 용이해짐

```jsx
// ES6
let str = `asdhasfhfsahsfhfshasfhsfahsfahsfahasfh
mxmxmxmxmxmxmxmmxmxmxmxmxmmxmxmxmxmxm`;
```

### 10. Default Parameter

- 함수의 매개변수 초기화
  
  - 기존에는 내부 작업이 필요
  - ES6에서는 필요하지 않음
  
  ```jsx
  // ES5
  function myFunc(a, b) {
      var a = a || 100
      var b = b || 200
      return a + b
  }
  console.log(myFunc(100))    // 300
  
  // ES6
  const myFunc = ( a = 100, b = 200 ) => a + b
  console.log(myFunc())       // 300
  ```

### 11. Module

- 모듈이란?
  - 재사용하기 위한 코드 조각
  - 세부사항은 캡슐화, API 부분만 외부에 노출
- type에 module을 추가시키고 확장자를 mjs로 변경하여 사용
- 모듈은 모듈 스코프 가지며, import와 export 키워드를 이용하여 사용

```jsx
<script type="module" src="lib.mjs"></script>
```