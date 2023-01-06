> You are running `create-react-app` 4.0.2, which is behind the latest release (4.0.3).
>
> We no longer support global installation of Create React App.
>
> Please remove any global installs with one of the following commands:
> - npm uninstall -g create-react-app
> - yarn global remove create-react-app
>
> The latest instructions for creating a new app can be found here:
> https://create-react-app.dev/docs/getting-started/

### 상황
`npx create-react-app` 실행 도중 에러 발생.
`npm uninstall -g create-react-app`로 삭제 후 재설치해도 그대로 안 됨

### 해결법
`npm add create-react-app`를 해준다!  
같이 생기는 노드모듈 처리하기  

```
npm uninstall -g create-react-app
npm add create-react-app
npx create-react-app my-app
```
