## Vue
- Front-end Development : UI와 UX를 만들고 디자인하는 것 <-> Back-end Development
- Client-side frameworks : 프론트엔드(=클라이언트 측에서) 개발을 도와주는 JavaScript 기반의 프레임워크들 ex) Angular, React, vue
    - 역할과 목적 : 동적인 대화형 웹 애플리케이션을 쉽게 구축할 수 있게 한다.
- Single Page Application : 페이지 한 개로 구성된 웹 애플리케이션
    - 동작 방식 : 초기에 서버로부터 필요한 모든 정적 HTML을 한번에 가져옴 -> 이후 요청이 오면 프레임워크는 각 HTML요소에 적절한 동적 javascript코드를 실행해 DOM을 업데이트함<br/>
    => 이러한 방식을 CSR(Client-side Rendering)방식이라고 함


#### CSR의 장점과 단점
1. 장점
    - 매번 모든 데이터를 새로고침할 필요 없어 서버로 전송되는 데이터의 양을 최소화할 수 있다.
    - 프론트엔드와 백엔드의 역할이 구분되어 있어 대규모 웹 어플리케이션을 쉽게 관리할 수 있다.

2. 단점
    - 초기 페이지 구동 시에 속도가 느리다.
    - SEO(검색 엔진 최적화)에 적절하지 않다.

### Vue의 2가지 핵심 기능
1. 선언적 렌더링 (Declarative Rendering)
    - HTML을 확장하는 구문을 사용해 HTML이 javascript데이터를 기반으로 어떻게 보이는지 설명할 수 있다.
2. 반응형 (Reactivity)
    - 변경사항을 자동 추적하여 DOM을 효율적으로 업데이트한다.