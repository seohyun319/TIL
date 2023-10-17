## useNavigate() - react-router-dom의 navigate 사용

```jsx
const navigate = useNavigate();
return () => navigate(to, { replace, state });
```

`to`: url string

`replace`: true는 현재 페이지의 히스토리 날림 (스택 최상단의 url를 이동할 url로 대체). 뒤로가기 하면 히스토리 날린 페이지의 이전 페이지로 감. false는 바로 이전 페이지로

`state`: 라우트 사용하면서 state도 함께 넣어줄 수 있음. isFromMainPage: boolean 등의 상태를 넣어주는 식으로 사용. 

---

state 사용 시 useLocation 사용

```jsx
import { useLocation } from "react-router";

const { state } = useLocation();
```

---

useHistory처럼 navigate() 안에 -2, -1, 1, 2 넣어서 뒤로가기, 앞으로가기, 2 페이지 전으로 가기 등 사용 가능
