# JavaScript 기초

## History

- JavaScript의 탄생
  - 1994년 당시 넷스케이프 커뮤니케이션스 사의 Netscape Navigator(NN) 브라우저가 전세계 점유율을 80% 이상 독점하며 브라우저의 표준 역할을 함
  - 당시 넷스케이프에 재직 중이던 브랜던 아이크가 HTML을 동적으로 동작하기 위한 회사 내부 프로젝트를 진행 중 JS를 개발
  - JavaScript 이름 변천사
    - Mocha → LiveScript → JavaScript(1995)
  - 1995년 경쟁사 마이크로소프트에서 이를 채택하여 커스터마이징한 JScript를 만듦
  - IE 1.0에 탑재 → 1차 브라우저 전쟁의 시작
- 제1차 브라우저 전쟁
  - 넷스케이프 vs 마이크로소프트
  - 빌 게이츠 주도하에 MS는 1997년 IE 4를 발표하면서 시장을 장악하기 시작
- 제2차 브라우저 전쟁
  - MS vs Google
  - 2008년 Google
- 파편화와 표준화
  - 제1차 브라우저 전쟁 이후 수많은 브라우저에서 자체 자바스크립트 언어를 사용하게 됨
  - 서로 다른 자바스크립트가 만들어지면서 크로스 브라우징 이슈가 발생하여 웹 표준의 필요성 제기
  - 크로스 브라우징(Cross Browsing)
    - W3C에서 채택된 표준 웹 기술을 채용하여 각각의 브라우저마다 다르게 구현되는 기술을 비슷하게 만들되, 어느 한쪽에 치우치지 않도록 웹 페이지를 제작하는 방법론(동일성이 아닌)
    - 브라우저마다 렌더링에 사용하는 엔진이 다르기 때문
  - 1996년부터 넷스케이프는 표준 제정의 필요성을 주장
    - ECMA 인터내셔널(저보와 통신 시스템을 위한 국제적 표준화 기구)에 표준 제정 요청
  - 1997년 ECMAScript 1(ES1) 탄생
  - 제1차 브라우저 전쟁 이후 제기된 언어의 파편화를 해결하기 위해 각 브라우저 회사와 재단은 표준화에 더욱 적극적으로 힘을 모으기 시작
- JavaScript ES6+
  - 2015년 ES2015(ES6) 탄생
  - JavaScript의 고질적인 문제들 해결
- Vanilla JavaScript
  - 크로스 브라우징, 간편한 활용 등을 위해 많은 라이브러리 등장(jQuery 등)
  - ES6 이후 다양한 도구의 등장으로 순수 자바스크립트 활용의 증대



## Dom 조작

- Dom 관련 객체의 상속 구조
  - EventTarget
    - Event Listener를 가질 수 있는 객체가 구현하는 DOM 인터페이스
  - Node
    - 여러 가지 DOM 타입들이 상속하는 인터페이스
  - Element
    - Document 안의 모든 객체가 상속하는 가장 범용적인 인터페이스
    - 부모인 Node와 그 부모인 Event
- DOM 선택 - 선택 관련 메소드
  - document.querySelector(selector)
    - 제공하는 선택자와 일치하는 element 하나 선택
    - 제공한 CSS selector를 만족하는 첫 번째 element 객체를 반환(없으면 null)
  - document.querySelectorAll(selector)
    - 제공한 선택자와 일치하는 여러
  - getElementById(id)
  - getElementsByTagName(name)
  - getElementsByClassName(names)
- XSS(Cross-site Scripting)
  - 공격자가 입력 요소를 사용하여 웹 사이트 클라이언트 측 코드에 악성 스크립트를 삽입해 공격하는 방법
  - 피해자(사용자)의 브라우저가



## Event

- 개념
  - 네트워크 활동이나 사용자와의 상호작용 같은 사건의 발생을 알리기 위한 객체
  - 이벤트 발생
    - 마우스를 클릭하거나 키보드를 누르는 등 사용자 행동으로 발생할 수도 있음
    - 특정 메소드를 호출하여 프로그래밍적으로도 만들어낼 수 있음

