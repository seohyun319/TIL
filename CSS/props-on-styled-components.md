## styled-components에서 props로 조건부 스타일링

`(props.속성이름)` 형태보다 `({속성이름})` 형태가 더 짧고 직관적이다!

```js
const StyledText =
  styled.div <
  TextType >
  `
  font-size: ${({ size }) => size}rem;
  color: ${({ color }) => color};
  font-weight: ${({ bold }) => bold && "bold"};
`;
```

**공통 컴포넌트 만들기**

```js
type TextType = {
  children: React.ReactNode
  color?: string
  size?: number
  bold?: boolean
}

const Text = ({ children, color, size, bold }: TextType) => {
  return (
    <StyledText color={color} size={size} bold={bold}>
      {children}
    </StyledText>
  )
}

Text.defaultProps = {
  size: 1,
}

const StyledText = styled.div<TextType>`
  font-size: ${({ size }) => size}rem;
  color: ${({ color }) => color};
  font-weight: ${({ bold }) => bold && 'bold'};
`
```
