### 상황

input창에 아무것도 입력이 안 됨

### 원인

onChange 이벤트와 handleChange 함수는 잘 호출되는데 handleChange가 새 값을 어디로 보내줘야 될지 몰라서 state가 업데이트 안 됨

### 해결

name 속성 추가

```html
<input
  type="email"
  name="email"
  placeholder="ID"
  onChange="{handleInputChange}"
  value="{inputs.email}"
/>
```

참고 [링크](https://velog.io/@hyemison/%EB%A6%AC%EC%95%A1%ED%8A%B8-input-%EC%9E%85%EB%A0%A5-%EC%95%88-%EB%90%A8)
