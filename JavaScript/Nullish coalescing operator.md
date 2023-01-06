# nullish 병합 연산자 ??

`x = a ?? b`

- `a`가 `null`도 아니고 `undefined`도 아니면 `a`
- 그 외의 경우는 `b`
- `x = (a !== null && a !== undefined) ? a : b;`

### ??와 ||의 차이

- `||`는 첫 번째 *truthy* 값 반환.
    - 0이 들어오면 falsy한 값으로 취급해 null, undefined와 동일 취급
- `??`는 첫 번째 *정의된(defined)* 값 반환.
    - 0이 들어오면 null이나 undefined가 아니기에 0 반환

### ?? 정리

- 피연산자 중 ‘값이 할당된’ 변수를 빠르게 찾을 수 있음
- 변수에 기본값을 할당하는 용도로 사용 가능
- `??`의 연산자 우선순위는 대다수의 연산자보다 낮고 `?`와 `=` 보다는 높음 → 괄호 사용 권장
- 괄호 없이 `??`를 `||`나 `&&`와 함께 사용 금지: 안전성 관련 이슈 때문.

<br /><br />

[코어 자바스크립트 - 자바스크립트 기본](https://ko.javascript.info/nullish-coalescing-operator)
