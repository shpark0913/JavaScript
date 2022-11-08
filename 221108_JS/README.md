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
