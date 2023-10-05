## aspect-ratio: 종횡비. 비율

요소의 크기를 비율대로 조정할 수 있게 함. 

- 사용법    
    - width나 height 값을 지정 후 `aspect-ratio: 3/1`을 하면 너비 3 높이 1의 비율로 사이즈가 정해짐    
    - `aspect-ratio: 3`을 할 경우 너비 3 높이 1로 정해짐. (높이 기본값 1)
    - aspect-ratio를 지정하고 화면 너비에 맞는 max-height를 지정해줘서 비율은 유지한 채 반응형 대응을 해줬다!
    
- img 안 깨지게 같이 쓰는 법: img 부모에 aspect-ratio 지정하고 img에 object-fit: cover
- 예외 상황:
    1. 너비, 높이값 다 지정된 경우
    2. min/max-width/height가 지정된 경우
    3. 내용이 요소를 넘는 경우

[참고](https://mong-blog.tistory.com/entry/css-Aspect-Ratio-%EC%9A%94%EC%86%8C%EB%A5%BC-%EB%B9%84%EC%9C%A8%EB%8C%80%EB%A1%9C-%EC%A1%B0%EC%A0%95%ED%95%98%EA%B8%B0)
