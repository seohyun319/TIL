### 문제 상황
> Component selectors can only be used in conjunction with @emotion/babel-plugin, the swc Emotion plugin, or another Emotion-aware compiler transform.

Next.js와 styled-components(emotion) 사용 중, 새 컴퓨터에 세팅하니까 안 나던 에러가 남. 
Next.js 12버전부터는 babel 대신 swc를 이용해서 트랜스파일함.  
babel로 트랜스파일을 하지 않는데다가, @emotion/babel-plugin이 없어서 문제가 발생한 것.
emotion 뿐만 아니라 별도의 바벨 설정 필요한 라이브러리에서 발생하는 이슈


### 해결 방법
next.config.js 속성 설정
```js
const nextConfig = {
  ...
  compiler: {
    emotion: true,
  },
};
```

- [참고](https://nuhends.tistory.com/124) 
- [참고](https://cheolsker.tistory.com/39)
