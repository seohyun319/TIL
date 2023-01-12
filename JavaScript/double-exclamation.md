## !! (double exclamation)

다른 타입의 데이터를 boolean 타입으로 명시적으로 형 변환  
보통 null이나 undefined를 false로 변환할 때 사용 가능

--- 


false로 취급하는 값 목록

| 값 | 설명 |
| --- | --- |
| ”” | 빈 문자열 |
| false | 기본 boolean false |
| NaN | Not a Number |
| undefined | 정의되지 않은 값 |
| null | Null값 |
| 0 | 숫자 기본값 |


---


`!!!`: `!!`의 부정

```jsx
const num = 123
console.log(!!num) // true
console.log(!!!num) // false

const name = 'seohyun'
console.log(!!name) // true
console.log(!!!name) // false

const zero = 0
console.log(!!zero) // false
console.log(!!!zero) // true
```
