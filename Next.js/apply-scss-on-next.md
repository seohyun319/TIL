### next.js에 sass 적용하는 방법
`npm install sass` 로 설치

next.config.js에 
```js
const path = require('path')

module.exports = {
  sassOptions: {
    includePaths: [path.join(__dirname, 'styles')],
  },
}
```
적어두기.


### trouble shooting
> error - Failed to load next.config.js 

const path = require('path')를 안 해서 생긴 에러! 

---

참고 공식 문서 
- https://nextjs.org/docs/basic-features/built-in-css-support
- https://nextjs.org/docs/messages/next-config-error

