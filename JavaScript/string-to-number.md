## js에서 string을 number로 바꾸기

```js
const quantity = "12";
```

- `Number(quantity)`
  - 숫자+문자 조합의 경우 NaN(not a number) 리턴
  - 소수점 표시 가능
- `parseInt(quantity)`
  - 숫자+문자 조합의 경우 숫자까지만 형변환해 리턴, 문자+숫자 조합의 경우 NaN 리턴
  - 소수점 표시 불가. 소수점은 parseFloat()로.
  - 두 번째 파라미터로 진수 변환 가능
- `+quantity` : Unary Operator
  - true, false, null도 숫자로 변환 가능 (parseInt는 불가)
  - 숫자+문자 조합의 경우 NaN(not a number) 리턴
- `quantity * 1`
- `quantity / 1`
- `quantity - 0`
