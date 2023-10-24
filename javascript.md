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


#### Syntax1
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


#### Syntax2
1. 변수
- [권장 스타일 가이드](http://standardjs.com/rules-kokr.html)
- 변수명 작성 규칙
    - 카멜 케이스(camelCase): 변수, 객체, 함수에 사용
    - 파스칼 케이스(PascalCase): 클래스, 생성자에 사용
    - 대문자 스네이크 케이스(SNAKE_CASE): 상수(유일성)에 사용

- 변수 선언 키워드 : 블록 스코프 {}를 갖는 지역 변수를 선언함
    - let : 재할당O/재선언X/선언시 초기값X
    - const : 재할당X/재선언X/선언시 초기값O
    - var

2. 데이터 타입
- 원시 자료형 : 변수에 값이 직접 저장되는 자료형
    - number
    - srting
    - boolean : true/false
    - null / undefined : 변수의 값이 없음을 의도적으로 명시할때 / 변수 선언 이후 값을 할당하지 않은 경우 자동 할당되는 값

- 참조 자료형 : 변수에 객체의 주소가 저장되는 자료형
    - 모든 객체값(Object, Array, Funtion)

3. 연산자
- 할당 연산자 : 오른쪽 값을 왼쪽 피연산자에 할당('='), '+=', '-='와 같은 단축 연산자 지원
- 증감 연산자 : '++', '--' 앞뒤의 피연산자를 1씩 증가시키거나 감소시킴 **(변수와 증감 연산자의 순서에 주의)**
- 비교 연산자 : 부등호로 표현하고 결과값은 true/false로 반환됨
- 동등/일치 연산자 : 동등 연산자는 '=='로 비교. 같은 값으로 '취급'되는 경우 true로 반환, 일치 연산자는 '==='로 비교하여 완벽히 같은 값인 경우만 true로 반환
- 논리 연산자 : and(&&), or(||), not(!), 단축 평가 지원

4. 조건문
```
*일반적 구조
if (조건식) {
    표현식
} else if (조건식) {
    표현식
} else {
    표현식
}

*단축식-조건(삼항)연산자 사용
if (조건식) ? 'true일 경우의 반환값':'false일 경우의 반환값'

```

5. 반복문
- while문
```
while (진행 조건) {
    표현식
    증감식
}
```
- for문
```
for (초기문; 조건문; 증감문) {
    표현식
}
```
- for ..in / for ..of
```
* for ..in
for (const 매개변수 in 열거가능한 객체) {
    표현식
}

* for ..of
for (const 매개변수 of 반복가능한 객체/배열) {
    표현식
}
```
- for ..in문은 객체의 속성값을 순서없이 무작위로 반환함 --인덱스의 순서가 중요한 배열에서는 사용하지 않음
- for ..of문은 반복 가능한 배열에 대한 값을 반환함


- 반복문 사용시의 변수 선언 구분
    - for문 : 최초 정의한 매개변수를 계속해서 재할당하며 사용하므로 let으로 선언해줄 것
    - for ..in / for ..of문 : 재할당이 아닌, 매 반복마다 새롭게 변수 선언을 하는 것이므로 const를 사용할 것