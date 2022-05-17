### 문제 상황

도커에서 실행하고 있는 프로젝트의 프론트를 next.js로 진행하고 있는데 수정 사항을 저장을 하고 새로고침을 해도 반영이 안 된다. 도커 상에서 클라이언트를 처음에만 로딩하고 끝내버린다.
클라이언트 개발에 hot-reloading이 안 돼서 매번 도커를 껐다 켜고 약 5분을 도커 껐다 켜는 실행시간으로 버리는 리스크 때문에 즉각적으로 확인을 못하고 감으로 코드를 적는 치명적인 상황

### 에러 원인

맥북을 쓰는 다른 팀원은 정상적으로 잘 되는 거 보면 윈도우 상의 문제인 것 같다.
usePolling 기본값이 MacOS에선 true이고, 나머지(윈도우)는 false라서..... 윈도우 도커 유저만 겪는 문제인 거로......

### 해결 방법

next.config.js에 다음 내용을 적는다.

```jsx
module.exports = {
  webpackDevMiddleware: (config) => {
    config.watchOptions = {
      poll: 1000,
      aggregateTimeout: 300,
    };
    return config;
  },
};
```

- 해결을 위해 열심히 한 각종 시도 보러가기
  - https://github.com/seohyun319/HanALL/issues/11#issuecomment-1127552564
