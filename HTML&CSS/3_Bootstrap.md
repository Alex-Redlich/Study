## Bootstrap
- 부트스트랩 사용 이유 : HTML&CSS 사용하는 속도가 매우 빨라짐
- 만들어진 컴포넌트가 많다 -> 가져다 사용만 하자!

- 순서
- 1. 부트스트랩 공식문서 들어가기
- 2. 원하는 요소 찾기
- 3. 사용하기

### CDN
- Content Delivery(Distribution) Network
- 컨텐츠(CSS, JS, Image, Text 등)를 효율적으로 전달하기 위해 여러 노드를 가진 네트워크에서 데이터를 제공하는 시스템.
- 개별 end-user의 가까운 서버를 통해 빠르게 전달 가능(지리적 이점)
- 외부 서버를 활용함으로써 본인 서버의 부하가 적어짐

#### 단위
- px
- %
- vw : viewport width
- vh : viewport height
- rem : html의 폰트사이즈에 비례한다
- 브라우저 <html>의 root 글꼴 크기는 16px

#### 마진 상쇄 현상
- 마진이 겹치면 제일 큰 마진만 적용된다.
- 겹쳐서 들어가는 것, 그래서 작은 마진들은 상쇄된다.


### 반응형 웹(Responsive Web)
- 다양한 화면 크기를 가진 디바이스들이 등장함에 따라 Responsive Web Design 개념이 등장
- 반응형 웹은 별도의 기술 이름이 아닌 웹 디자인에 대한 접근 방식, 반응형 레이아웃 작성에 도움이 되는 사례들의 모음 등을 기술하는데 사용되는 용어
- 예시 
  - Media Queries, Flexbox, Bootstrap Grid System, The viewport meta tag
  
### Bootstrap Grid System
- The Grid System
  - CSS가 아닌 편집 디자인에서 나온 개념으로 구성 요소를 잘 배치해서 시각적으로 좋은 결과물을 만들기 위함
  - 기본적으로 안쪽에 있는 요소들의 오와 열을 맞추는 것에서 기인
  - 정보 구조와 배열을 체계적으로 작성하여 정보의 질서를 부여하는 시스템
- Web에서도 Grid system이 들어오다
- 요소들의 디자인과 배치에 도움을 주는 시스템
- 기본요소 
  - Column : 실제 컨텐츠를 포함하는 부분
  - Gutter : 칼럼과 칼럼 사이의 공간(사이 간격)
  - contatiner : Column들을 담고 있는 공간
  - Bootstrap grid System
    - Bootstrap grid System은 flexbox로 제작됨
    - container, rows, column으로 컨텐츠를 배치하고 정렬
    - 반드시 기억해야 할 2가지
    - 1. 12개의 column
    - 2. 6개의 gird breackpoints
- 