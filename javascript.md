## JavaScript
1. 자바 스크립트의 역사
```
- 1990년 팀 버너스리 경에 의해 웹이 탄생하고, 웹 브라우저가 대중화되었다.
- 당시 최초의 상용 웹 브라우저였던 Netscape사의 Netscape Navigaor, 넷 스케이프는 단순한 텍스트 페이지만의 지원이 아닌 웹의 '동적 기능 개발' 이라는 목적 이상으로 스크립트 언어 Mocha를 개발
- 이후 JavaScript로 이름을 변경하였다.
```
- 1차 브라우저 전쟁 (1995-2001)
    - 자바 스크립트의 개발 이후 많은 회사들이 자체적 자바스크립트에 기반한 자체적 커스텀 모델을 개발하면서 웹 표준 없이 자바스크립트가 파편화 되기 시작함
    - Netscaope사와 Microsoft사의 경쟁구도, IE 무료배포라는 강력한 무기를 가지고 MS가 끝내 2002년 시장 점유율 약 96를 달성함.
    - 이후 웹 표준화에 대한 인식하는 계기가 되었고 ECMA(European Computer Manufactures Association), 정보와 통신시스템의 비영리 표준 기구에서 ECMAScript라는 표준 언어를 배포하게 됨

- 2차 브라우저 전쟁 (2004-2017)
    - IE와 FireFox의 양립구도로 진행되다가 2008년 크롬 브라우저 출시 이후 3년만에 업계 1위가 됨
    - 크롬 브라우저가 시장 점유율 1위가 될 수 있었던 배경으로 웹 표준의 준수를 꼽을 수 있었고, 이로 인해 웹 표준의 중요성이 대두됨
    - 이후 웹의 기능이 크게 확장되며 웹 애플리케이션의 비약적인 발전을 이끌어감

2.  자바 스크립트의 현재
```
- 웹 표준의 통일을 기반으로 현재는 웹 브라우저 시장이 다양화 되어있음
- 기존의 자바 스크립트는 브라우저에서만 웹페이지의 동적 기능을 구현했으나,
이후 Node.js와 같은 서버 사이드 분야 뿐만 아니라 아야한 프레임워크와 라이브러리에서도 쓰이는 필수적 언어가 됨.
```

### DOM(The Document Object Model)
- 웹 페이지 문서의 요소를 구조화된 객체로 제공하여 프로그래밍 언어로 페이지에 접근 및 조작할 수 있도록 하는 API
- DOM에서는 모든 요소, 속성, 텍스트가 document라는 전체 페이지 객체의 자식으로 구성됨(DOM tree라는 상속 구조의 객체 트리가 존재)


#### Syntax
1. document 객체</br>
    웹 페이지 객체, 기타 요소에 접근하기 위한 진입점, 최상단노드
2. 선택</br>
    document.querySelector() --단일요소</br>
    docuemnt.querySelectorAll() --다중요소</br>

3. 조작</br>
    3-1. 속성 조작</br>
        - 클래스 속성 조작</br>
        element.classList.add() --클래스 속성값을 추가</br>
        element.classList.remove() --클래스 속성값을 삭제</br>
        element.classList.toggle() --클래스가 존재하면 삭제 존재하지 않으면 추가</br>
        - 일반 속성 조작</br>
        element.getAttribute() --해당 요소에 지정된 값을 반환</br>
        element.setAttribute(name, value) --지정된 요소의 속성값 설정, 기존 속성이 있으면 갱신</br>
        element.removeAttribute() --요소에서 지정된 속성을 제거</br>
    3-2. HTML 콘텐츠 조작</br>
        element.textContent = value</br>
    3-3. DOM 요소 조작</br>
        document.createElement(tagName) --새로운 태그 생성</br>
        Node.appendChild() --특정 태그를 노드리스트의 마지막 자식으로 추가</br>
        Node.removeChild() --DOM에서 자식노드 삭제
    3-4. style 조작</br>
        element.style.(styleElement) = value --스타일을 인라인 값으로 추가
