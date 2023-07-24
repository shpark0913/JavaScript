## 1. Lazy Loading, Pagination의 개념

1. Lazy Loading이란
   
   - 페이지를 읽어들이는 시점에 당장 필요하지 않은 리소스 로딩을 추후에 하는 기술
   - 중요하지 않은 리소스들은 필요할 때 로드되어야 함

2. Pagination이란
   
   - 검색 결과를 가져올 때, 데이터를 쪼개 번호를 매겨 일부만 가져오는 기법
   - pagination이 사용된 페이지 예
   
   ![1.png](C:\Users\parksihyun\Desktop\1.png)
   
   
   
   api server로 원하는 page의 값을 요청한다.
   
   ![2.png](C:\Users\parksihyun\Desktop\2.png)
   
   
   
   해당하는 data와 image data를 fetch한다.
