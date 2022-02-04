# HTML

- W3C HTML5
- WHATWG 표준
- 이제 익스플로러는 브라우저가 아님
- Can I use에서 사용 가능한 확인 가능
  - 회색 : 알 수 없음
  - 빨간색 : 지원하지 않음
  - 갈색 : 일부 지원
  - 초록색 : 지원
- `!` + `tab` 누르면 HTML 기본 포맷 자동완성



## 개발환경 설정



- `ctrl` + `shift` + `I`
- `F12`
- 마우스 우클릭 후 검사
- 



- HTML

- 하이퍼 텍스트 : 참조(하이퍼 링크) 를 통해

- Hyper Text Markup Language

- Markup Language : 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어

- HTML, Markdown

- 웹 페이지를 작성(구조화)하기 위한 언어

- .html

- HTML 기본 구조

  - `html` : 문서 최상위 요소
  - `head` : 문서 메타데이터 요소
    - 문서 제목, 인코딩, 스타일, 외부 파일 로딩 등
    - 일반적으로 브라우저에 나타나지 않는 내용
  - `body` : 문서 본문 요소
    - 실제 화면 구성과 관련된 내용

  ```html
  <!DOCTYPE html>
  <html lang="ko">
  <head>
      <meta charset="UTF-8"
            <title>Document</title>
  </head>
  <body>
      
  </body>
  </html>
  ```

  - head 예시

    - `<title>` : 브라우저 상단 타이틀
    - `<meta>` : 문서 레벨 메타데이터 요소
    - `<link>` : 외부 리소스 연결 요소(CSS 파일, favicon 등)
    - `<script>` : 스크립트 요소(JavaScript 파일/코드)
    - `<style>` : CSS 직접 작성

    ```html
    <head>
        <title>HTML 수업</title>
        <meta charset="UTF-8">
        <link
    </head>
    ```

  - Open Graph Protocol

    - 메타 데이터를 표현하는 새로운 규약
    - HTML 문서의 메타 데이터를 통해 문서의 정보를 전달
    - 메타정보에 해당하는 제목, 설명 등을 쓸 수 있도록 정의

  - DOM(Document Object Model) 트리

    - 텍스트 파일인 HTML 문서를 브라우저에서 렌더링하기 위한 구조
    - HTML 문서에 대한 모델을 구성
    - HTML 문서 내의 각 요소에 접근 / 
    - 들여쓰기가 되어 있지 않아도 태그로 동작 가능
    - 가독성(유지보수)을 위해 들여쓰기(2 space)

  - 요소(element)

    - 여는(시작) 태그와, 닫는(종료) 태그, 태그 사이 위치한 내용(contents)으로 구성
    - 태그는 내용을 감싸는 것으로 그 정보의 성격과 의미를 정의
    - 내용이 없는 태그들
      - `br` : 개행
      - `hr` : 수평선
      - `img` : 이미지(링크)
      - `input`
      - `link`
      - `meta`
    - 요소는 중첩(nested) 될 수 있음
    - 요소의 중첩을 통해 하나의 문서를 구조화
    - 여는 태그와 닫는 태그의 쌍을 잘 확인해야 함(오류 반환하지 않고 레이아웃 깨진 상태로 출력)

  - 속성(attribute)

    - 태그별 사용할 수 있는 속성은 다름

    - ```html
      <a href="https://google.com"></a>  <!-- a + tab 자동 완성-->
      ```

    - 속성을 통해 태그의 부가적인 정보를 설정할 수 있음

    - 요소는 속성을 가질 수 있으며 경로나 크기와 같은 추가적인 정보 제공

    - 요소의 여는 태그에 작성하며 보통 이름과 값이 하나의 쌍으로 존재

    - HTML Global Attribute : 태그와 상관없이 모든 HTML 요소가 공통으로 사용 가능한 속성

      - `id` : 문서 전체에서 유일한 고유 식별자 지정
      - `class` : 공백으로 구분된 해당 요소의 클래스 목록(CSS, JS에서 요소 선택하거나 접근)
      - `data-*` : 페이지에서 개인 사용자 정의 데이터를 저장하기 위해 사용
      - `style` : inline 스타일
      - `title` : 요소에 대한 추가 정보 지정
      - `tabindex` : 요소의 탭 순서

- 시맨틱 태그

  - HTML5에서 의미론적 요소를 담은 태그
    - 기존 영역을 의미하는 `div` 태그를 대체하여 사용
    - 기존에도 h1, table 등이 있었으나 영역에 대한 의미를 추가
  - 대표적인 태그 목록
    - `header` : 문서 전체나 섹션의 헤더(머리말 부분)으로 `head`와 구분
    - `nav` : 내비게이션
    - `aside` : 사이드에 위치한 공간, 메인 콘텐츠와 관련성이 적은 콘텐츠
    - `section` : 문서의 일반적인 구분으로 콘텐츠의 그룹을 표현
    - `article` : 문서, 페이지, 사이트 안에서 독립적으로 구분되는 영역
    - `footer` : 문서 전체나 섹터의 푸터(마지막 부분)
  - Non semantic 요소는 div, span 등이 있으며 h1, table 태그들도 시맨틱 태그로 볼 수 있음
  - 검색 엔진 최적화(SEO)를 위해 메타태그, 시맨틱 태그 등을 통한 마크업을 효과적으로 활용해야 함

## HTML 문서 구조화

- 인라인 / 블록 요소
  - CSS에서 안내
- 텍스트 요소
  - `<a></a>` : href 속성을 활용하여 다른 URL로 연결하는 하이퍼링크 생성
  - `<b></b>` 굵은 글씨 요소
  - `<strong></strong>` 강조하고자 하는 요소(시맨틱 태그, 보통 굵은 글씨, 시각적 차이는 없음)
  - `<i></i>` : 기울임 글씨 요소
  - `<em></em>` : 강조하고자 하는 요소(시맨틱 태그, 보통 기울임 글씨, 시각적 차이는 없음)
  - `<br>` : 텍스트 내 줄 바꿈 생성
  - `<img>` : src 속성을 활용하여 이미지 표현
  - `<span></span>` : 의미 없는 인라인 컨테이너
- 그룹 콘텐츠
  - `<p></p>` : 하나의 문단(paragraph)
  - `<hr>` : 문단 레벨 요소에서의 주제의 분리를 의미하며 수평선으로 표현(A Horizontal Rule)
  - `<ol></ol>` : 순서가 있는 리스트(ordered)
  - `<ul></ul>` : 순서가 없는 리스트(unordered)
  - `<pre></pre>` : HTML에 작성한 내용 그대로 표현. 보통 고정폭 글꼴 사용되고 공백문자 유지
  - `<blockquote></blockquote>` : 
- table
  - table의 각 영역을 명시하기 위해 `<thead>`, `<tbody>`, `<tfoot>` 요소 활용
  - `<tr>`으로 가로 줄을 구성하고 내부에는 `<th>` 혹은 `<td>`로 셀 구성
  - `colspan`, `rowspan` 속성을 활용하여 셀 병합
  - `<caption>`을 통해 표 설명 또는 제목을 나타냄
- form
  - 정보(데이터)를 서버에 제출하기 위한 영역
  - 기본 속성
    - `action` : form을 처리할 서버의 URL
    - `method` : form을 제출할 때 사용할 HTTP 메소드(`GET` 혹은 `POST`)
    - `enctype` : `method`가 `POST`인 경우 데이터의 유형(이미지, 비디오 파일 등)
      - `application/x-www-form-urlencoded` : 기본값
      - `multipart/form-data` : 파일 전송 시(input type이 file인 경우)
      - ~~`test/plain` : HTML5 디버깅용(잘 사용되지 않음)~~
- input
  - 다양한 타입을 가지는 입력 데이터 유형과 위젯 제공
  - 대표 속성
    - `name` : form control에 적용되는 이름(이름/값 페어로 전송)
    - `value` : form control에 적용되는 값(이름/값 페어로 전송)으로 기본값 입력 가능
    - `required`, `readonly`, `autofocus`, `autocomplete`, `disabled` 등
- label을 클릭하여 input 자체의 초점을 맞추거나 활성화 시킬 수 있음
- 사용자는 선택할 수 있는 영역이 늘어나 웹/모바일 터치 환경에서 편하게 사용할 수 있음
- 



## CSS

- 스타일을 지정하기 위한 언어

  ```css
  h1 {					/* 선택자 */
      color: blue;		/* 선언 */
      font-size: 15px;	/* 속성: 값 */
  }
  ```

- CSS 구문은 선택자를 통해 스타일을 지정할 HTML 요소를 선택

- 중괄호 안에서는 속성과 값 하나의 쌍으로 이루어진 선언을 진행

- 각 쌍은 선택한 요소의 속성, 속성에 부여할 값을 의미

  - 속성 : 
  - 값 : 어떤 스타일

- 정의 방법

  - 인라인(inline)
    - 해당 태그의 속성에 직접 `style`을 적용
  - 내부 참조(embedding)
    - `<style>` 태그로 CSS 문법 사용
    - 길어지면 가독성 떨어짐
  - 외부 참조(link file)
    - 외부 CSS 파일을 `<head>` 내 `<link>`를 통해 불러오기
    - 재사용성 높음
  - styles : 해당 요소에 선언된 모든 CSS
  - computed : 해당 요소에 최종 계산된 CSS



## CSS Selectors

- 선택자 유형

  - 기본 선택자
    - 전체 선택자, 요소 선택자
    - 클래스 선택자, 아이디 선택자, 속성 선택자
  - 결합자
    - 자손 결합자
  - 의사 클래스/요소

- 요소 선택자

  - HTML 태그를 직접 선택

- 클래스 선택자

  - 

- 아이디 선택자

- 전체 선택자

- CSS 적용 우선순위

  1. 중요도(Importance) - 사용 시 주의
     - `!important`

  2. 우선순위(Specificity)
     - 인라인 > id(`#`) > class(`.`), ~~속성~~, ~~pseudo-class~~ > 요소, ~~pseudo-element~~ > 전체(`*`)

  3. CSS 파일 로딩 순서

- CSS 상속

  - CSS는 상속을 통해 부모 요소의 속성을 자식에게 상속
    - 속성 중에는 상속이 되는 것과 되지 않는 것들이 있음
    - 상속 되는 것 예시
      - Text 관련 요소(font, color, text-align), opacity, visibility 등
    - 상속되지 않는 것 예시
      - Box model 관련 요소(width, height, margin, padding, border, box-sizing, display)
      - position 관련 요소(position, top/right/bottom/left, z)
      - 



## CSS 기본 스타일

- 크기 단위
  - px(픽셀)
    - 픽셀 크기는 변하지 않기 때문에 고정적인 단위
  - %
    - 백분율 단위
    - 가변적인 레이아웃에서 자주 사용
  - em
    - (바로 위 부모 요소의) 상속 영향을 받음
    - 배수 단위, 요소에 지정된 사이즈에 상대적인 사이즈를 가짐
  - rem
    - (바로 위 부모 요소의) 상속 영향을 받지 않음
    - 최상위 요소(html)의 사이즈를 기준으로 배수 단위를 가짐
  - viewport
    - 웹 페이지를 방문한 유저에게 바로 보이게 되는 웹 콘텐츠의 영역(디바이스 화면)
    - 디바이스의 viewport를 기준으로
- 색상 단위
  - 색상 키워드
    - 대소문자 구분하지 않음
    - red, blue, black과 같은 특정 색을 직접 글자로 나타냄
  - RGB 색상
    - 6자리 표기가 일반적(3자리 표기도 있음)
    - `rgb()`, `hsl()` 함수 존재
    - 투명도 조절이 가능한 `rgba()`, `hsla()`
- CSS 문서 표현
  - 텍스트
    - 서체, 서체 스타일
    - 자간, 단어 간격, 행간, 들여쓰기 등
  - 컬러(`color`), 배경(`backgound-image`, `background-color`)
  - 기타 HTML 태그별 스타일링
    - 목록(`li`), 표(`table`)



## a

- 결합자(Combinators)
  - 자손 결합자
    - selectorA 하위의 모든 selectorB 요소
    - `selectorA selectorB`
  - 자식 결합자
    - selectorA 바로 아래의 selectorB 요소
    - `selectorA > selectorB`
  - 일반 형제 결합자
    - selectorA의 형제 요소 중 뒤에 위치하는 selectorB 요소를 모두 선택
    - `selectorA ~ selectorB`
  - 인접 형제 결합자
    - selectorA의 형제 요소 중 바로 뒤에 위치하는 selectorB 요소를 선택
    - `selectorA + selectorB`



## Box model

- Normal Flow : 모든 요소는 박스 모델, 위에서부터 아래로, 왼쪽에서 오른쪽으로 쌓임
- margin : 
- border : 테두리 영역
- padding : 테두리 안쪽의 내부 여백 요소에 적용된 배경색, 이미지는 padding까지 적용
- content : 글이나 이미지 등 요소의 실제 내용
- margin/padding shorthand
  - 하나 : 상하좌우
  - 둘 : 상하, 좌우
  - 셋 : 상, 좌우(중), 하
  - 넷 : 상, 우, 하, 좌(시계방향)
- box-si



## CSS

- `display` 속성에 따라 크기와 배치가 달라짐
- `display: block`
  - 줄 바꿈이 일어나는 요소
  - 화면 크기 전체의 가로 폭을 차지
  - 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음
- `display: inline`
  - 줄 바꿈이 일어나지 않는 행의 일부 요소
  - content 너비만큼 가로 폭을 차지
  - `width`, `height`, `margin-top`, `margin-bottom`을 지정할 수 없음
  - 상하 여백은 `line-height`로 지정
- 대표적인 블록 레벨 요소
  - `div` / `ul`, `ol`, `li` / `p` / `hr` / `form` 등
- 대표적인 인라인 레벨 요소
  - `span` / `a` / `img` / `input`, `label` / `b`, `em`, `i`, `strong` 등
- `display: inline-block`
  - block과 inline 레벨 요소의 특징을 모두 가짐
  - inline처럼 한 줄에 표시 가능하고 block처럼 `width`, `height`, `margin` 속성을 모두 지정할 수 있음
- `display: none`
  - 해당 요소를 화면에 표시하지 않고, 공간도 부여하지 않음
  - `visibility: hidden` : 해당 요소가 **공간은 차지**하나 화면에 표시하지 않음



## CSS position

- position으로 위치의 기준을 변경
- 문서 상에서 요소의 위치를 지정
- `static` : 모든 태그의 기본 값(기준 위치)
  - 일반적인 요소의 배치 순서에 따름(좌측 상단)
  - 부모 요소 내에서 배치될 때는 부모 요소의 위치를 기준으로 배치
- 아래는 좌표 프로퍼티(`top`, `bottom`, `left`, `right`)를 사용하여 이동 가능
  - `relative` : 상대 위치
    - 자기 자신의 `static` 위치를 기준으로 이동(normal flow 유지)
    - 레이아웃에서 요소가 차지하는 공간은 static일 때와 같음
  - `absolute` : 절대 위치
    - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃 공간을 차지하지 않음(normal flow 벗어남)
    - **`static`이 아닌** 가장 가까이 있는 부모/조상 요소를 기준으로 이동(없는 경우 `body`)
  - `fixed` : 고정 위치
    - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃 공간을 차지하지 않음(normal flow 벗어남)
    - 부모 요소와 관계없이 viewport를 기준으로 이동(스크롤 시에도 항상 같은 곳에 위치)
  - `sticky` : 부분 고정?
    - 부모 요소 범위에서 `fixed` 처럼
- emmet

