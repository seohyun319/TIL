## module.scss와 classnames 같이 사용하기

```js
export const Button = ({ children, color }: buttonType) => {
  return <button className={classNames('Button', size)}>{children}</button>;
};
```
이렇게 했었는데 적용되지 않음. → css를 module로 사용하기 때문에 안에서 읽어와야 하기 때문. (next.js는 전역 css 말고는 module로 안 해주면 에러 남) 

\`${style.Button}\` 등을 시도해봤는데 style["Button"]으로 적용해야 정상 작동한다.

> classnames은 함수 인자에 여러 개 전달할 때 문자열 쉽게 조합할 수 있도록 해주는 라이브러리
> 

---

적용한 방법


```js
import classNames from "classnames";
import style from "./Button.module.scss";

export const Button = ({ children, color }: buttonType) => {
  return (
    <button className={classNames(style["Button"], style[color])}>
      {children}
    </button>
  );
};
```

```css

@mixin button-color($color) {
  background: $color;
  &:hover {
    background: lighten($color, 10%);
  }
  &:active {
    background: darken($color, 10%); 
  }
}

.Button {
  border: none;
  border-radius: 10px;
  padding: 0 1rem;
  margin-left: 5px;
  cursor: pointer;
  height: 2rem;
  width: 100px;

  &.yellow {
    @include button-color($concept-yellow);
  }

  &.pink {
    @include button-color($concept-pink);
  }

  &.white {
    @include button-color(white);
  }

}
```

