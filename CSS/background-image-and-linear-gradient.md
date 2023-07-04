## background-image와 linear-gradient 동시에 넣기

```jsx
// 이렇게 각각 있을 땐 둘 다 적용되지 않음
background-image: url(${getImageSrc(BackgroundImgName)});
background: linear-gradient(99.47deg, #2660ff -3.66%, #81e1ff 113.52%);

// 콤마(,)로 구분해 한 번에 background로 넣기
background: url(${getImageSrc(BackgroundImgName)}),
    linear-gradient(99.47deg, #2660ff -3.66%, #81e1ff 113.52%);
```
