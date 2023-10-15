### 오류 상황

> Function type notation must be parenthesized when used in a union type.
> 

```tsx
interface PropType {
  onClick?: MouseEventHandler<HTMLElement> | () => void;
}
```

### 해결 방법

컴파일러는 해당 구문을 `(MouseEventHandler<HTMLElement> | ()) => void`로 인식하기 때문! 괄호로 원하는 대로 감싸주면 됨

```tsx
interface PropType {
  onClick?: MouseEventHandler<HTMLElement> | (() => void);
}
```

---

[스택오버플로우 Typescript Union type with a function](https://stackoverflow.com/questions/47748830/typescript-union-type-with-a-function)
