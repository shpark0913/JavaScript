## JavaScript 공부

JavaScript에 대해 공부한 내용을 정리한 레포지토리입니다.

---



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
    - **예상치 못한 결과가 발생할 수 있으므로 특별한 경우를 제외하고 사용하지 않음**
