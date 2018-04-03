
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

### 질문

- MVVM 패턴 적용 현황?
- javascript vs typescript 실무 적용 현황?

# 2. 개발 환경 설정 및 첫 번째 프로젝트

## 개발 환경 설정하기

- 크롬 브라우저
- 아톰 에디터
  - seti-ui Themes install
  - atom-material-syntax-dark Themes install
  - language-vue Packages install
- Node.js
- Vue.js devtools (크롬 확장 플러그인)

## Hello Vue.js! 프로젝트 만들기

- Root Component
  - Vue 애플리케이션의 최상위 컴포넌트

# 3. 화면 개발 필수 단위 - 인스턴스 & 컴포넌트

## 뷰 인스턴스

- 뷰 인스턴스 생성
```javascript
new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js!'
  }
});
```
  - 뷰 인스턴스 생성자
  - 뷰 인스턴스 옵션
    - data, template, methods, created
    - el: 뷰 인스턴스 렌더링 시, 그려질 위치의 DOM 지정
- 뷰 인스턴스 유효 범위
  - 뷰 인스턴스 옵션 속성이 적용되는 범위
  - el 속성으로 지정한 태그 하위 요소들로 범위 제한
- 뷰 인스턴스 라이프 사이클
  - beforeCreate
  - created
  - beforeMount
  - mounted
  - beforeUpdate
  - updated
  - beforeDestroy
  - destroyed

## 뷰 컴포넌트

- 조합하여 화면을 구성할 수 있는 블록
- 재활용 형태로 관리
- 컴포넌트 등록
  - 지역 컴포넌트
```javascript
new Vue({
  component: {
    'component name': 'component contents'
  }
});
```
  - 전역 컴포넌트
```javascript
Vue.component('component name', {
  // component contents
});
```

## 뷰 컴포넌트 통신

- 컴포넌트 마다 고유한 유효 범위 존재
  - 다른 컴포넌트의 값을 직접 사용할 수 없음
  - 애플리케이션이 모두 동일한 데이터 흐름 갖게 됨
  - Vue.js에서 정의한 데이터 전달 방법을 준수해야 함
- 상위 > 하위 컴포넌트 데이터 전달
  - props 속성
```javascript
Vue.component('child-component', {
  props: ['props 속성 이름']
});
```
```html
<child-component v-bind:props 속성이름="상위 컴포넌트의 data 속성"></child-component>
```
- 하위 > 상위 컴포넌트 이벤트 전달
  - 이벤트 발생 $emit()
```javascript
this.$emit('이벤트명');
```
  - 이벤트 수신 v-on:
```html
<child-component v-on:이벤트명="상위 컴포넌트의 메서드명"></child-component>
```
- 같은 레벨 간 컴포넌트 통신
  - 이벤트 버스
    - 추가 인스턴스 1개 생성
    - 이벤트 전송 .$emit()
    - 이벤트 수신 .$on()
```javascript
var eventBus = new Vue();
```

```javascript
methods: {
  메서드명: function() {
    eventBus.$emit('이벤트명', 데이터);
  }
}
```

```javascript
methods: {
  crested: function() {
    eventBus.$on('이벤트명', function(데이터) {
      ...
    });
  }
}
```
