### 날짜 ISOString 변환 시 GMT 반영하기

```js
const timezoneOffset = new Date().getTimezoneOffset() * 60 * 1000;
const curDate = new Date(Date.now() - timezoneOffset)
  .toISOString()
  .slice(0, 16);
```

```html
<input
  name="startAt"
  type="datetime-local"
  <!-- curDate를 defaultValue로 지정해 현재시각이 자동 설정되도록 함 -->
  defaultValue={curDate}
  onChange={handleInputChange}
></input>
```
