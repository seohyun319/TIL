# 즉시실행함수 IIFE (Immediately-invoked function expression)
: 정의되자마자 즉시 실행되는 함수

함수를 ()로 감싸서 실행

```jsx
(function () {
    console.log("IIFE");
})();

// 화살표 함수로도 사용 가능
(() => {
    console.log("IIFE");
})();
```

사용 이유

- 필요 없는 전역 변수의 생성 감소
- private한 변수 생성 가능

[참고](https://jongminfire.dev/java-script-%EC%A6%89%EC%8B%9C%EC%8B%A4%ED%96%89%ED%95%A8%EC%88%98-iife)
