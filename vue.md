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


### Syntax
1. computed VS method
- computed: 의존된 반응형 데이터를 자동으로 추적하는 속성(함수)
    - 의존하는 데이터가 변경될 때만 재평가
    - 반환되는 값은 computed ref
- computed가 하는 역할을 method도 거의 유사하게 할 수 있지만 computed속성은 계산된 값이 캐시데이터 형태로 저장되면서 여러곳에서 사용될 때 중복 계산을 방지함
- 반면 method는 호출될 때마다 데이터를 렌더링

2. conditional Rendering
- v-if: 표현식 값의 true/false값을 기반으로 요소를 조건부로 렌더링 (v-else-if, v-else와 같이 사용), 조건문의 결과값이 false라면 요소가 아예 렌더링 되지 않음
- v-show: 조건문을 가진다는 점은 v-if와 비슷하나 결과값에 따라 요소의 가시성을 전환한다는 점이 차이점

3. List Rendering
- v-for: 요소 또는 템플릿 블록을 여러번 렌더링 하는 속성 
- for with key: key는 반드시 고유하며 식별 가능한 값을 쓸 것. (index는 쓸 수 없음, 계속해서 업데이트되기 때문에 고유성에 어긋남)
- *주의사항* : 동일한 요소에서 v-if와 v-for을 함께 쓰지 않는다. if가 먼저 실행되어서 해당 요소를 못 찾을 수 있음

4. watchers
- 반응형 데이터를 감시하고, 감시하는 데이터가 변경되면 콜백 함수를 호출
- computed VS watch: 모두 데이터의 변화를 감지하고 처리한다는 공통점이 있으나, computed는 미리 계산된 값을 반환하고 watch는 변화를 감지하면 특정 작업을 수행한다는 점에 차이가 있음.
- *주의사항* : 모두 감시(의존)하는 데이터의 원본을 직접 변경하지 않는다. 변경하면 호출의 무한 굴레에 빠지게 됨
- computed의 반환값도 변경하지 말 것. 직접 변경한다면 computed 함수의 의미가 없음

5. Lifecycle Hooks
- Vue 인스턴스의 생애주기 동안 특정 시점에 실행되는 함수
    - onMounted: Vue 컴포넌트 인스턴스가 초기 렌더링 되면 작업 수행
    - onUpdated: 반응형 데이터의 변경으로 인해 DOM이 업데이트 되면 작업 수행