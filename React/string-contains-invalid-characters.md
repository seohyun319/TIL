### 문제 상황

svg 아이콘을 export한 후, 다른 파일에서 import해서 쓰려고 할 때 발생
> The string contains invalid characters.

```jsx
// assets/icon/index.tsx
export { default as ClickIcon } from "./clickIcon.svg";

// 사용하는 파일
import { ClickIcon } from "assets/icon";
// 컴포넌트처럼 사용
<ClickIcon />
```

### 해결 방법

img src로 쓰는 상황이 아니라 ReactComponent로 사용할 땐 ReactComponent로 import해야 한다.

```jsx
export { ReactComponent as ClickIcon } from "./clickIcon.svg";
```

---

[스택오버플로우](https://stackoverflow.com/questions/63517356/receiving-invalidcharactererror-string-contains-an-invalid-character-from-imp)
