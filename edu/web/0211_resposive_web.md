# 반응형 웹

- 웹 페이지 디자인 형태
  - 고정폭 레이아웃(Fixed-width)
    - 브라우저 크기가 변해도 콘텐츠가 변화하지 않음
  - 유동적 레이아웃(Liquid layouts)
    - 이미지 및 글씨 등 영역이 유동적으로 변화함
  - 별도의 사이트
    - 디바이스에 따른 별도의 사이트(도메인)로 구분됨
  - 반응형 레이아웃(Responsive layouts)
    - 디스플레이 종류에 따라 화면의 크기가 자동으로 변하도록 만든 웹 페이지 접근 기법
    - 미디어 쿼리를 활용하여 CSS 작성



## 미디어 쿼리(Media Query)

- CSS에서 @media 키워드를 활용하여 브라우저 및 디바이스 등 환경에 따라 CSS를 적용하는 방법
  - media-type : `all`, `print`, `screen`, `speech`
  - media-feature-rule : `orientation`, `width`, `height` 등



## 웹 개발 가이드

- HTML/CSS 스타일 가이드 예시
  - [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html#CSS_Style_Rules)
    - 구글은 id 속성 사용을 금지하고, 알파벳 순으로 속성 작성
  - [NHN Coding Convention](https://nuli.navercorp.com/upload/2020/6672a2b7-abdd-411e-8a50-362911bc7999_Coding_Conventions_for_Markup.pdf)
    - NHN은 일부 약속된 레이아웃에서만 id 속성을 활용하고, 레이아웃 관련성에 따라 속성 작성
- BEM(Block Element Modifier) 방법론 : 네이밍 방법론
  - Block
    - 재사용 가능하고 기능적으로 독립적인 개체
    - `.block`
  - Element
    - Block의 구성 요소
    - 독립적으로 활용되지 않음(블록 내에서 의미)
    - `.block__elem`
  - Modifier
    - Block이나 element의 속성
    - 다른 형태(color, size)나 행동(disabled, checked)
    - `.block-modifier block__elem--modifier`



## 웹 페이지 추가 구성 요소

- Favicon(favorite icon)
  - 사이트를 대표하는 아이콘으로 브라우조 주소창, 탭, 북마크 바 등에 표시됨
  - 사용자가 웹 사이트를 쉽게 시각적으로 식별하는데 사용
  - 일반적으로 브랜드 로고와 동일한 것으로 사용하여 브랜드 인지도를 높임
  - [Favicon 생성기](https://favicon.io)
  
- Icon
  - 일반적인 웹 사이트에서 활용되는 아이콘은 이미지가 아닌 i 태그로 구성되어 있음
  - Font Awesome, Material Icons(Google), Bootstrap Icons
- 웹 폰트
  - 일반적으로 사용자 컴퓨터에 폰트가 없는 경우 원하는 폰트가 보여지지 않아 웹 폰트로 적용
  - Google Fonts



## Bootstrap 활용

- SCSS
  - CSS를 만들기 위한 도구로 변수, 상속, mixin 등의 개념을 통해 가독성과 재사용성을 높임
  - 일반적으로 SCSS로 개발하고 CSS로 변환하여 활용 가능하게 함
  - Sass
- 코드 경량화(minify)
  - 웹 사이트 접속 시 모든 소스코드는 네트워크를 통해 전송
  - 더욱 빠른 다운로드를 위해 파일의 공백 및 개행 문자를 제거하여 경량화
  - 확장자명 앞에 `.min`
