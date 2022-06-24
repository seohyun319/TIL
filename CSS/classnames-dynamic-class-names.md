### classnames에서 동적 클래스명 사용법
```js
let buttonType = 'primary';
classNames({ [`btn-${buttonType}`]: true });
```

적용 - boolean 타입 사용 & module.scss를 style로 import해 사용


`{[style.shadow]: shadow,}`

```js
export const Button = ({ children, color, shadow, onClick }: buttonType) => {
  return (
    <button
      className={classNames(style["Button"], style[color], {
        [style.shadow]: shadow,
      })}
      onClick={onClick}
    >
      {children}
    </button>
  );
};
```

---

참고 https://github.com/JedWatson/classnames#readme
