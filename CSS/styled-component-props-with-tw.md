## twin.macro (tw)에서 변수 props와 같이 사용하기
- tw 공식문서에서도 styled로 감싸고 그 안에서 사용
- props 여러 개 지정하려면 interface 쓰는 게 깔끔해짐
  ```js
  const BoxButton = styled.div(({ isOpen }: { isOpen: number }) => [
    tw`
    w-[2rem] h-[2rem]
    m-1
    flex items-center justify-center
    cursor-pointer
    `,
    isOpen ? tw`bg-red-50` : tw`bg-gray-200`,
  ]);
  ```
  
[참고 공식 문서](https://github.com/ben-rogerson/twin.macro/blob/master/docs/styled-component-guide.md)
