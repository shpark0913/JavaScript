## JavaScript 기초 문법

- 세미콜론(semicolon)
  
  - JavaScript는 세미콜론을 선택적으로 사용 가능
    
    - 없다면 ASI에 의해 자동으로 세미콜론 삽입됨
      
      - ASI란? 
        
         : Automatic Semicolon Insertion, 자동 세미콜론 삽입 규칙

- 들여쓰기와 코드 블럭
  
  - JavaScript는 <mark>2칸 들여쓰기</mark>를 사용
  
  - <mark>블럭(block)</mark>은 if, for, 함수에서 중괄호 <mark>{ }</mark> 내부를 말함
    
    - python : 들여쓰기를 이용해 코드 블럭을 구분
    
    - JavaScript : 중괄호 { } 사용해 코드 블럭을 구분

- 주석
  
  - 한 줄 주석     : //
  
  - 여러 줄 주석 : /*   */

- 변수와 식별자
  
  - 식별자
    
    - 변수를 구분할 수 있는 변수명을 말함
    
    - 반드시 문자, 달러(\$) 또는  밑줄(\_) 로 시작
    
    - 대소문자를 구분하며, 클래스명 외에는 모두 소문자로 시작
      
      - **카멜 케이스(camelCase)**
        
        - 변수, 객체, 함수에 사용
      
      - **파스칼 케이스(PascalCase)**
        
        - 클래스, 생성자에 사용
      
      - **대문자 스네이크 케이스(SNAKE_CASE)**
        
        - 상수(constants)에 사용
        
        - 상수 : 개발자의 의도와 상관없이 변경될 가능성이 없는 값
    
    - 예약어 사용 불가능
      
      - 예약어 예시 : for, if, function 등
  
  ---
  
  
  
  - 변수
    
    - <mark>let</mark>
      
      - 블록 스코프 지역 변수를 선언
      
      - 추가로 동시에 값을 초기화(선언과 동시에 원하는 값으로 초기화 가능)
      
      - 재할당 가능
      
      - 재선언 불가능
    
    - <mark>const</mark>
      
      - 블록 스코프 읽기 전용 상수를 선언
      
      - 추가로 동시에 값을 초기화(선언 시 반드시 초기값 설정해야)
      
      - 재할당 불가능
      
      - 재선언 불가능
    
    - var
      
      - 변수를 선언
      
      - 추가로 동시에 값을 초기화
      
      - 재할당 가능
      
      - 재선언 가능
      
      - ES6 이전에 사용되던 키워드 
      
      - 호이스팅이 되기 때문에, const와 let 권장
        
        - 호이스팅이란?
          
          - <mark>50쪽임</mark>
      
      - 함수 스코프를 가짐
      
      - <mark>변수 선언 시 var, const, let 중 하나 사용하지 않으면 자동으로 var로 선언</mark>
    
    - **선언, 할당, 초기화**란?
      
      - 선언
        
        - 변수를 생성하는 행위 또는 시점
      
      - 할당
        
        - 선언된 변수에 값을 저장하는 행위 또는 시점
      
      - 초기화
        
        - 선언된 변수에 처음으로 값을 저장하는 행위 또는 시점
    
    - 블록 스코프
      
      - if, for, 함수 등의 중괄호({ }) 내부를 가리킴
      
      - 블록 스코프를 가지는 변수는 블록 바깥에서 접근 불가능
      
      - **var은 함수 내에서만 지역변수로 유지됨. let과 const의 경우 함수가 아닌 블록 단위에서 지역 변수로 선언됨. 따라서 var는 함수 스코프를 가지고, const와 let은 블록 스코프를 가지는 것**