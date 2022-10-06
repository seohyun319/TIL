### 문제 상황
query로 넘겨준 값들을 못 읽어옴
- 해당 url
  ```js
  <Link
    href={{
      pathname: "/spacing",
      query: { page: 1, sort: "hits" },
    }}
    passHref
  > ... </Link>
  ```

- 서버사이드의 context 로그
  ```
  ServerRouter {
  client  |   route: '/spacing',
  client  |   pathname: '/spacing',
  client  |   query: {},
  client  |   asPath: '/spacing?page=1&sort=hits,
  client  |   isFallback: false,
  client  |   basePath: '',
  client  |   locale: undefined,
  ...
  ```
query에 page가 담겨야 하는데 빈 값으로 나옴! 



### 해결 방법
혹시나 해서 `getStaticProps`를 `getServerSideProps`로 바꾸고 로그 찍어보니까 잘 나왔다 ^-T...  

이거 때문인 듯 (공식문서 [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes))
> Pages that are statically optimized by Automatic Static Optimization will be hydrated without their route parameters provided, i.e query will be an empty object ({}).  
> After hydration, Next.js will trigger an update to your application to provide the route parameters in the query object.



<br />


**배경**
- 데이터를 getStaticProps로 받아옴 
- → sort와 page에 따라서 api 요청이 달라져야 하는데 현재 CSR에서 잘 돌아가는 페이지네이션이랑 정렬 선택은 어떻게 연동하지? 생각해보니 페이지 변경 등을 CSR에서만 처리하면서 URL이 고정되는 방식은 SEO-Friendly하지 않다! 
- → dynamic route로 하자니 페이지와 정렬 둘 다 client/pages에 새 파일을 만들어서 관리해줘야 하나? 그렇지만 URL이 spellings/1/hits 이런 식으로 되는데 SEO가 잘 인식할까? 그리고 보기에도 좋지는 않다. 파일 여러 개 만들면서 오히려 코드가 덜 깔끔해질 것 같은데...  
- → query로 관리하면 되지 않을까? 
- → ssg 로그에서 왜 쿼리를 못 읽지? 

의 순서로 여기까지 왔고 해결됐다! 

데이터가 유동적이지 않고 한 번 생성되면 그대로 유지돼서 static이 적합하다고 생각했는데, age와 sort에 따라서 페이지네이션/재정렬하면서 api 요청을 새로 하니까 serverSide로 해도 괜찮을 것 같다!  
그렇지만 데이터 패칭에는 빌드 시에 다 만들어놓는 getStaticProps가 더 빠를 것 같긴 해서 나중에 다시 생각해 봐야겠다. 이렇게 쿼리스트링으로 처리하는 게 보기에는 좋은데 아예 dynamic routes 사용해서 페이지 이동을 시키는 게 나을지... 

---

**문제 해결된 ssr 코드**
```js
export const getServerSideProps: GetServerSideProps = async (context) => {
  const page = context.query?.page as string;
  const sort = context.query?.sort as string;
  const spacings = await getSpacingList(sort, +page); // `+`page: parse string to number
  return {
    props: {
      spacings,
    },
  };
};
```

