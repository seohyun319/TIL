## position: absolute 중앙정렬 with transform && !calc

- position absolute이면서 가운데정렬이면서 40픽셀 위로 가기
    
    ```css
    export const CenterComponent = styled.div`
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%) translateY(-40px);
    `;
    ```
    
    - 중앙정렬: top, left에 50% 해서 가운데로 밂 → transform으로 요소 사이즈만큼 반대로 이동시킴
    - `transform: translateY(calc(100% - 40px));`
        - calc로 한번에 → 브라우저가 해당 값 필요할 때마다 매번 해석해야…
    - `transform: translateY(100%) translateY(-40px);`
        - 각각 → parse time에 컴파일됨
        - 이렇게 해야 효과적으로 잘 작동하고, 안전함

---

****[CSS - position:absolute 가운데, 중앙 정렬하기](https://myhappyman.tistory.com/163)****

**[Not possible to use CSS calc() with transform:translateX in IE](https://stackoverflow.com/questions/21469350/not-possible-to-use-css-calc-with-transformtranslatex-in-ie)**
