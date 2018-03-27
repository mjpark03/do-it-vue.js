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
