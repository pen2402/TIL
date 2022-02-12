# CSS Layout

## Float

- 박스를 왼쪽 혹은 오른쪽으로 이동시켜 텍스트를 포함한 인라인 요소들이 주변을 wrapping 하도록 함
- 요소가 Normal flow를 벗어난 부동 상태
- 속성
  - `none` : 기본값
  - `left` : 요소를 왼쪽으로 띄움
  - `right` : 요소를 오른쪽으로 띄움
- Clearing Float
  - 이후 요소에 대하여 Float 속성이 적용되지 않도록 Clearing 필수
  - `::after` : 선택한 요소의 맨 마지막 자식으로 가상 요소를 하나 생성
    - 보통 `content` 속성과 함께 요소 장식용 콘텐츠를 추가할 때 사용
  - `clear` 속성을 부모 요소에 부여
- 레이아웃 구성하기 위해 필수적으로 활용되었으며 최근에는 Flexbox, Grid 등장과 함께 사용도가 낮아짐
- Float 활용 전략 - Normal Flow에서 벗어난 레이아웃 구성
  - 원하는 요소들을 Float로 지정하여 배치
  - 부모 요소에 반드시 Clearing Float를 하여 이후 요소부터 Normal Flow를 가지도록 지정




## Flexbox

- 행과 열 형태로 아이템들을 배치하는 1차원 레이아웃 모델
- 축
  - main axis(메인 축, 기본적으로 `row`)
  - cross axis(교차 축)
- 구성요소
  - Flex Container(부모 요소)
    - Flexbox 레이아웃을 형성하는 가장 기본적인 모델
    - Flex Item들이 놓여있는 영역
    - `display` 속성을 `flex` 혹은 `inline-flex`로 지정
  - Flex Item(자식 요소)
    - 컨테이너에 속한 콘텐츠(박스)
- Flexbox는 수동 값 부여 없이 수직 정렬 가능하고 아이템의 너비와 높이 혹은 간격을 동일하게 배치
- 속성
  - 배치 설정
    - `flex-direction`
      - main axis 기준 방향 설정
      - 역방향의 경우 HTML 태그 선언 순서와 시각적으로 다르니 유의(웹 접근성에 영향)
    - `flex-wrap`
      - 아이템이 컨테이너를 벗어나는 경우 해당 영역 내에 배치되도록 설정
      - 기본적으로 컨테이너 영역을 벗어나지 않도록 함
      - `nowrap` : 한 줄에 배치(기본값)
      - `wrap` : 넘치면 그 다음 줄로 배치
    - `flex-flow`
      - `flex-direction`과 `flex-wrap`의 shorthand
      - `flex-dirention`과 `flex-wrap`에 대한 설정 값을 차례로 작성
  - 공간 나누기
    - `justify-content`(main axis)
      - Main axis를 기준으로 공간 배분
    - `align-content`(cross axis)
      - Cross axis를 기준으로 공간 배분(아이템이 한 줄로 배치되는 경우 확인할 수 없음)
    - `justify-content` & `align-content` 속성
      - `flex-start` : 아이템들을 axis 시작점으로(기본값)
      - `flex-end` : 아이템들을 axis 끝쪽으로
      - `center` : 아이템들을 axis 중앙으로
      - `space-between` : 아이템 사이의 간격을 균일하게 분배
      - `space-around` : 아이템을 둘러싼 영역을 균일하게 분배(아이템을 기준으로 양쪽에 분배)
      - `space-evenly` : 전체 영역에서 아이템 간 간격을 균일하게 분배
  - 정렬
    - `align-items`
      - 모든 아이템을 cross axis를 기준으로 정렬
    - `align-self`
      - 개별 아이템을 Cross axis 기준으로 정렬
      - 컨테이너가 아닌 개별 아이템에 적용되는 속성
    - `align-items` & `align-self` 속성
      - `stretch` : 컨테이너를 가득 채움
      - `flex-start` : 위
      - `flex-end` : 아래
      - `center` : 가운데
      - `baseline` : 텍스트 baseline에 기준선을 맞춤
  - 기타 속성
    - `flex-grow` : 남은 영역을 해당 아이템에 분배
    - `flex-shrink` : 부족한 영역을 해당 아이템에서 축소
    - `flex-basis` : 아이템의 기본 크기(공백 크기)를 결정(기본값 : `0`, 설정 후 `auto`)
    - `order` : 배치 순서(기본값 : `0`)



## Bootstrap

- Content Delivery(Distribution) Network(CDN)
  - 콘텐츠(CSS, JS, Image, Text 등)를 효율적으로 전달하기 위해 여러 노드에 가진 네트워크에 데이터를 제공하는 시스템
  - 가까운 서버를 통해 유저에게 빠르게 전달 가능
  - 외부 서버를 활용함으로써 서버 부하가 적어짐
- spacing
  - `m` : margin
  - `p` : padding
  - `t` : top
  - `b` : bottom
  - `s` : left
  - `e` : right
  - `x` : left, right
  - `y` : top, bottom
  - `0` : 0 rem(0px)
  - `1` : 0.25 rem(4px)
  - `2` : 0.5 rem(8px)
  - `3` : 1 rem(16px)
  - `4` : 1.5 rem(24px)
  - `5` : 3 rem(48px)
- 반응형 웹 디자인(Responsive Web Design)
  - 다양한 화면 크기의 디바이스들이 생겨남에 따라 등장한 개념
  - 특정 기술 이름이 아닌 웹 디자인에 대한 접근 방식, 반응형 레이아웃 작성 사례 등을 기술하는 용어




## Bootstrap Grid System

- Grid system(web design)
  - 요소들의 디자인과 배치에 도움을 주는 시스템
  - 기본 요소
    - Column : 실제 콘텐츠를 포함하는 부분
    - Gutter : Column 사이 공간(간격)
    - Container : Column들을 담고 있는 공간
- Bootstrap Grid System
  - flexbox로 제작
  - container, row, column으로 콘텐츠를 배치하고 정렬
  - 특징
    - 12개의 column
    - 6개의 grid breakpoints(`xs`, `sm`, `md`, `lg`, `xl`, `xxl`)
  - 12칸 넘어가면 다음 줄로 표현
  - nesting : 부모 영역을 다시 12칸으로, column 내 column
  - offset : 번호를 통해 해당 영역에 배치

