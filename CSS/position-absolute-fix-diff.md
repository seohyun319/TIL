## position 속성 (absolute fixed 차이)
- position: `static`
    - 기본값
- position: `relative`
    - static처럼 일반적 순서에 따라 표시하지만 offset(top, left, bottom, right)을 자기 자신 기준으로 적용
- position: `absolute`
    - static이 아닌 속성이 부여된 부모 기준으로 위치 설정 (속성 부여된 부모 없을 경우 body 기준)
        - 상위 컴포넌트에 `position: relative` 적용 시 부모의 시작점 기준으로 offset(top, left, bottom, right) 적용 가능

            > 부모를 relative로 static 흐름에서 벗어나게 한 다음 그 아래 자식이 부모를 중심으로 absolute(절대) 좌표를 사용
            > 
    - 스크롤 시 위치 고정 X
- position: `fixed`
    - 부모 속성에 관계 없이 화면에서 절대적인 위치 차지.
    - 스크롤해도 위치 고정

---

[CSS 포지션 속성 설명: absolute, fixed, relative 차이 설명](https://oneroomtable.tistory.com/entry/CSS-%ED%8F%AC%EC%A7%80%EC%85%98-%EC%86%8D%EC%84%B1-%EC%84%A4%EB%AA%85-absolute-fixed-relative-%EC%B0%A8%EC%9D%B4-%EC%84%A4%EB%AA%85)

[CSS의 absolute position 작동 메커니즘 이해](https://www.daleseo.com/css-position-absolute/)
