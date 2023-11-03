## border에 gradient 적용하기

border의 색을 투명하게 하고, background-image에 border 색 설정

**background-origin:** 배경 이미지를 어느 영역부터 채워나갈지를 정함. (기본값 : padding-box)

> padding-box : 안쪽 여백 영역 왼쪽 위부터 채움.
> 
> 
> border-box : 테두리 영역 왼쪽 위부터 채움.
> 
> content-box : 내용 영역 왼쪽 위부터 채움.
> 
> initial : 기본값으로 설정.
> 
> inherit : 부모 요소의 속성값을 상속받음.
> 

```css
.profile-image {
  border: 2px solid transparent;
  background-origin: border-box;
  background-size: cover;
  background-image: linear-gradient(
    135deg,
    #0038ff 25%,
    #00ff66 56.25%,
    #ffd600 76.56%
  );
}
```


---


[border에 그라데이션 넣기](https://velog.io/@dltjsgho/css-border%EC%97%90-%EA%B7%B8%EB%9D%BC%EB%8D%B0%EC%9D%B4%EC%85%98-%EB%84%A3%EA%B8%B0)