## CSS

### CSS Box Model

![박스모델](../image/HTML_CSS//캡처_12.PNG)

- 모든 요소는 네모(박스모델)이고, 위에서부터 아래로, 왼쪽에서 오른쪽으로 쌓인다.
- 모든 HTML 요소는 box 형태로 되어있음
- 하나의 박스는 네 부분(영역)으로 이루어짐
  - content
  - padding
  - border
  - margin

![박스모델구성](../image/HTML_CSS//캡처_13.PNG)

#### Box model 구성(margin) - 상하좌우
.margin{
    margin-top:10px;
    margin-right:20px;
    margin-bottom:30px;
    margin-left:40px;
}

![마진](../image/HTML_CSS//캡처_14.PNG)

#### Box model 구성(padding) - 상하좌우
.margin-padding{
    margin:10px;
    padding:30px;
}

![마진](../image/HTML_CSS//캡처_15.PNG)

#### Box model 구성(border) -상하좌우
.border{
    border-width:2px;
    border-style:dashed;
    border-color:black;
}

![보더](../image/HTML_CSS//캡처_16.PNG)

#### box-sizing
- 기본적으로 모든 요소의 box-sizing은 content-box
  - padding을 제외한 순수 contents 영역만을 box로 지정
- 다만, 우리가 일반적으로 영역을 볼 떄는 border까지의 너비를 100px 보는 것을 원함
  - 그 경우 box-sizing을 border-box으로 설정

![box-sizing](../image/HTML_CSS//캡처_17.PNG)

### 개발자 도구
- 웹 브라우저 크롬에서 제공하는 개발과 관련된 다양한 기능을 제공
- 주요 기능
  - Elements -DOM 탐색 및 CSS 확인 및 변경
  - Styles - 요소에 적용된 CSS 확인
  - Computed - 스타일이 계산된 최종 결과
  - Event Listeners - 해당 요소에 적용된 이벤트(JS)
- Sources, Network, Performance, Application, Security, Audits 등

#### HTML - elements
- elements : 해당 요소의 HTML 태그

#### HTML DOM 조작하기
- Element에서 HTML 태그 구조를 탐색하며 추가, 삭제, 이동, 편집 등이 가능

![DOM](../image/HTML_CSS//캡처_18.PNG)
![DOM](../image/HTML_CSS//캡처_19.PNG)

#### CSS - styles, computed
- styles : 해당 요소에 선언된 모든 CSS
- computed : 해당 요소에 최종 계산된 CSS

![CSS](../image/HTML_CSS//캡처_20.PNG)

#### CSS 조작하기
- 우선순위, 파일 로딩 등에 의해 적용되고 있는 모든 CSS를 확인할 수 있음
- 원하는 속성을 제거해보거나, 값을 변경하여 결과를 바로 확인할 수 있음
- 박스 모델에 해당하는 영역 값을 쉽게 변경 할 수 있음
- 해당 요소에 대한 스타일을 다양하게 추가해 볼 수 있음
- 상속 관계도 확인 가능

### CSS Layout

### CSS Display
- 모든 요소는 네모(박스모델)이고, 좌측 상단에 배치
- display에 따라 크기와 배치가 달라진다.

#### 대표적으로 활용되는 display
- display: block
  - 줄 바꿈이 일어나는 요소 (다른 elem를 밀어낸다!)
  - 화면 크기 전체의 가로 폭을 차지한다.
  - 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음
- display: inline
  - 줄 바꿈이 일어나지 않는 행의 일부 요소
  - content를 마크업 하고 있는 만큼만 가로 폭을 차지한다.
  - width, height, margin-top, margin-bottom을 지정할 수 없다.
  - 상하 여백은 line-height로 지정한다.

#### 블록 레벨 요소와 인라인 레벨 요소
- 블록 레벨 요소와 인라인 레벨 요소 구분
- 대표적인 블록 레벨 요소
  - div/ ul,ol,li / p / hr / form 등
- 대표적인 인라인 레벨 요소
  - span / a / img / input,label / b, em, i, strong 등

#### block
- block의 기본 너비는 가질 수 있는 너비의 100%
- 너비를 가질 수 없다면 자동으로 부여되는 margin

#### inline
- inline의 기본 너비는 컨텐츠 영역만큼만

![정렬관계](../image/HTML_CSS//캡처_21.PNG)

#### display
- display : inline-block
  - block과 inline 레벨 요소의 특징을 모두 가짐
  - inline처럼 한 줄에 표시 가능하고, block처럼 width, height, margin 속성을 모두 지정할 수 있음
- display : none
  - 해당 요소를 화면에 표시하지 않고, 공간조차 부여되지 않음
  - 이와 비슷한 visibility : hidden은 해당 요소가 공간을 차지하나 화면에 표시만 되지 않는다.

### CSS position

- 문서 상에서 요소의 위치를 지정(어떤 기준으로 어디에 배치시킬지)
- static : 모든 태그의 기본 값(기준 위치)
  - 일반적인 요소 배치 순서에 따름(좌측 상단)
  - 부모 요소 내에서 배치될 떄는 부모 요소의 위치를 기준으로 배치 됨
- 아래는 좌표 프로퍼티(top,bottom,left,right)를 사용하여 이동 가능
  - relative : 상대위치
    - 자기 자신의 static 위치를 기준으로 이동(normal flow 유지)
    - 레이아웃에서 요소가 차지하는 공간은 static 일 떄와 같음(normal position 대비 offset)
  - absolute : 절대 위치
    - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃에 공간을 차지하지 않음(normal flow에서 벗어남)
    - static이 아닌 가장 가까이 있는 부모/조상 요소를 기준으로 이동(없는 경우 body)
  - fixed : 고정 위치
    - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃에 공간을 찾이하지 않음(normal flow에서 벗어남)
    - 부모 요소와 관계없이 viewprot를 기준으로 이동
      - 스크롤 시에도 항상 같은 곳에 위치함
  - sticky : 스크롤에 따라 static -> fixed로 변경
    - 속성에 적용한 박스는 평소에 문서 안에서 position : static 상태와 같이 일반적인 흐름에 따르지만 스크롤 위치가 임계점에 이르면 postion:fixed와 같이 박스를 화면에 고정할 수 있는 속성

- CSS 원칙 3가지
  - 모든 요소는 네모(박스모델), 좌측 상단에 배치
  - display에 따라 크기와 배치가 달라짐
  - position으로 위치의 기준을 변경
    - relative : 본인의 원래 위치
    - absolute : 특정 부모의 위치
    - fixed : 화면의 위치

