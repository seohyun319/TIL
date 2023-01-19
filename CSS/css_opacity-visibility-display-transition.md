## 화면에 요소를 보이지 않게 하는 방법

```css
opacity: 0;
visibility: hidden;
display: none;
transform: scale(0);
z-index: -1;
```

---

## opacity / visibility / display

| Property | Painted | In layout (공간 차지) | Pointer (클릭) events | Keyboard events | 
| --- | --- | --- | --- | --- |
| `opacity: 0;` | X | O | O | O |
| `visibility: hidden;` | X | O | X | X |
| `display: none;` | X | X | X | X |
- display: none의 경우 렌더링 트리에 안 그려짐. display: block이 된 후에 렌더링 트리에 들어가고, 그제야 레이아웃과 페인트 과정 일어남. transition을 쓰려면 none 상태와 block 상태의 opacity 값 차이 비교할 수 있어야 하는데 none 상태의 opacity는 애초에 존재 X(렌더링 트리에 없어서) → transition 사용 불가
- 공간 차지: 화면에 안 보여도 공간은 그대로 차지함. visibility: hidden과 opacity:0
- pointer event & keyboard event: 접근성 트리에서 삭제 시 해당 event 사용 불가. visibility: hidden과 display: none

---

## transition

: 이전 프로퍼티의 상태와 이후 프로퍼티의 상태를 비교해 그 차이를 부드럽게 이어주는 애니메이션. (주로 숫자 연산 가능한 속성에 사용) 

## 보임/안 보임 애니메이션 넣는 방법

1. **transition이 아니라, keyframe animation 활용**
    - display:none → block으로 가는 애니메이션은 초기값 설정으로 애니메이션 구현이 가능하지만 <br />display:block → none으로 가는 애니메이션은 불가능
        - none이 된 순간 렌더 트리에서 삭제됨 → 애니메이션 재생도 전에 삭제
    - 사라질 때 애니메이션이 필요 없으면 사용 가능
2. **display none을 안 쓰고 구현**
    1. display 대신 visibility 사용
        - `visibility: hidden` 상태와 `visibility: visible` 상태를 서로 비교 가능, transition 애니메이션 사용 가능
        - 주의: `transition-property`를 all로 해야 함
    2. pointer-event 활용
        - 화면 상에 안 보이게만 처리하고 싶을 때 - `opacity: 0` 지정하고 `pointer-events: none`으로 마우스 클릭 이벤트 삭제
            - 다시 화면 상에 나타내야 하는 경우 `pointer-events: auto`로 지정하면 됨

[css-display-none-애니메이션-수정하기](https://songsong.dev/entry/css-display-none-%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98-%EC%88%98%EC%A0%95%ED%95%98%EA%B8%B0)

[opacity/visibility/display 차이점](https://stackoverflow.com/questions/14731049/visibilityhidden-vs-displaynone-vs-opacity0)
