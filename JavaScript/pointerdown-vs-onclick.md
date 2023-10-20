## onPointerDown과 onClick의 차이
- `onPointerDown`
    - 마우스 버튼이 눌릴 때 작동
    - 적용 범위: Element, Document, Window
        - cf) `onMouseDown` 적용 범위: Element
    - captures the right/left/middle clicks
- `onClick`
    - 마우스 버튼이 눌린 후 뗄 때 작동
    - only captures the left click.

---

[스택오버플로우 - pointerdown vs onclick: what is the difference?](https://stackoverflow.com/questions/69899775/pointerdown-vs-onclick-what-is-the-difference)
