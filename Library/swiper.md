## 캐러셀 라이브러리 swiper 사용법

```jsx
import SwiperCore, { Autoplay } from "swiper";
import { Swiper, SwiperSlide } from "swiper/react";

SwiperCore.use([Autoplay]);

return (
  <StyledSwiper 
    loop
    grabCursor
    autoplay={{
      delay: 3000,
      disableOnInteraction: false,
    }}
  >
    <SwiperSlide>첫 번째 배너</SwiperSlide>
    <SwiperSlide>두 번째 배너</SwiperSlide>
  </StyledSwiper>
)
```

## 트러블 슈팅

> property 'modules' does not exist on type 'intrinsicattributes & swiper

### 원인

공식 문서에는 `modules={[Autoplay]}`로 사용하라고 나와있지만 정의된 타입이 다름. (문서에는 `SwiperModule[]`, 실제로는 `SwiperComponent[]`. 

swiper 버전 문제로 인해 발생. 현재 공식 문서는 v8 기준이나 프로젝트에서 사용하고 있는 것은 v6. 과거 버전을 지원 안 하지만 아카이브에서 [v6 버전 문서](http://web.archive.org/web/20210825021924/https://swiperjs.com/swiper-api#parameters) 발견… 모듈 사용법이 달라졌다!

### 해결

`SwiperCore.use([Autoplay])`를 사용해 해결.
