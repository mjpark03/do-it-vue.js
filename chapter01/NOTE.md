# 1. Vue.js 소개

## 01-1. Vue.js란 무엇인가?

- 정의
  - 프런트엔드 프레임워크 및 라이브러리
- 장점
  - 배우기 쉬움
  - React와 Angular에 비해 성능 및 속도 우수함
    - [Results for js web frameworks benchmark](http://www.stefankrause.net/js-frameworks-benchmark7/table.html)
  - React의 가상 DOM 및 Angular의 데이터 바인딩 특성 모두 갖고 있음

### 질문

- 프런트엔드 엔지니어가 비교하는 Vue.js vs React vs Angular?
- 가상 DOM 이란?

## 01-2. Vue.js 특징

- MVVM 패턴에서 ViewModel에 해당하는 라이브러리
  - DOM Listener
    - 예) Button 클릭 감지
  - Data Binding
    - 예) 검색 결과에 해당하는 데이터를 모델에서 가져와, 화면에 전달
- 컴포넌트 기반 프레임워크
- React와 Angular의 장점 결합
  - Angular의 양방향 데이터 바인딩
    - 화면 값과 모델의 값이 동기화되어 함께 변경
  - React의 단방향 데이터 흐름
    - 상위 컴포넌트에서 하위 컴포넌트로만 데이터 흐름 가능
  - React의 가상 DOM
    - 특정 DOM 변경 시, 화면 전체를 다시 렌더링하지 않음
