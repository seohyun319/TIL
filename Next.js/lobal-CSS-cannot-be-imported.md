> lobal CSS cannot be imported from files other than your Custom <App>. Due to the Global nature of stylesheets, and to avoid conflicts, Please move all first-party global CSS imports to pages/_app.js. Or convert the import to Component-Level CSS (CSS Modules).
> 
  
### 원인
css 파일을 name.scss로 선언해서 해당 파일을 전역 파일로 인식했다! globals.scss만 _app.tsx에 import해주면 되는 줄 알았는데, next.js에서는 글로벌을 제외한 나머지 css 파일은 전부 module로 만들어야 한다.
  
### 해결 방법
css 파일을 name.module.scss로 생성
  
  --- 
  
참고 링크
- [공식 문서: Global CSS Must Be in Your Custom \<App>](https://nextjs.org/docs/messages/css-global)
