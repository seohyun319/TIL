## z-index가 동작하지 않는 이유 및 해결책

1. z-index가 설정되지 않은 경우 stacking order에 따름: 나중에 오는 element가 더 위에 있음
2. element에 position이 설정되지 않은 경우 
    - position: relative 설정해주니 해결!
    - position이 설정된 요소는 설정되지 않은 요소보다 위에 위치함 → position 없는 요소에 z-index를 설정해도 position이 있는 요소가 더 위에 위치
3. opacity, transform같은 속성들을 설정한 경우: element가 새로운 stacking context에 배치됨 
    - 명시적으로 설정하면 됨.
4. 부모의 z-index 레벨 때문에 element가 더 낮은 stacking context 안에 있는 경우 
    - 부모 element의 z-index를 확인하고 설정해주면 됨.
    - 부모에 설졍했는데도 안 되면 최상단 부모끼리 비교해서 설정해보자!

<br />

⭐개발자도구에서 확인하고 싶을 때: `Layers`에서 3D로 볼 수 있음.
> 개발자도구 → more tools → layers

---

참고

- [4 reasons your z-index isn’t working (and how to fix it)](https://coder-coder.com/z-index-isnt-working/)
- [👨🏻‍💻 How to solve the Z-index issue Within 1 minute😲😲](https://dev.to/sharmakushal/how-to-solve-the-z-index-issue-within-1-minute-4pn9)
