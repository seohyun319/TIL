## DOM으로 prop 전달 막는 법 - transient props 이용

### 오류 상황
> React does not recognize the `isSelected` prop on a DOM element. If you intentionally want it to appear in the DOM as a custom attribute, spell it as lowercase `isselected` instead. If you accidentally passed it from a parent component, remove it from the DOM element.
> 

### 해결책
isSelected는 단순히 스타일링을 위해 사용한, 카멜케이스로 표기해야 하는 styled-components용 변수이기 때문에 변수명 앞에 `$`을 붙여 해결.
`$`사인으로 표기한 props는 `styled-components`에서 `transient props`라고 명명되어 있는데, 이는 단순히 스타일만을 위한 변수가 기본 React 노드로 전달되거나 DOM 요소로 렌더링되는 것을 방지할 때 사용 가능한 `prop`이다!

isSelected를 transient props로 변경해 해당 prop을 DOM에서 감지하지 않고 styled-components에서만 사용하게 함

[공식문서](https://styled-components.com/docs/api#transient-props)

[참고블로그](https://velog.io/@young_pallete/Styled-components-DOM-issue)
