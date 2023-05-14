## 데이터를 새로 받아오는 방법들
- `useMutation`의 `refetchQueries` 옵션: GraphQL스러운, 권장하는 방법.
    - query로 read만 하는 상황에서 새 데이터를 받아오고 싶은 상황이면 refetch가 개발자가 코드 쓰기에 편함
    - 데이터가 바뀌어야 하는 상황(특정 동작 완료 시점 등)에 사용
- refetch: 함수로 사용.
- network-only: 캐싱 없이 매번 새 값 받아옴. 성능 상으로 조금 불리함.
    - `{ fetchPolicy: "network-only" }`
        - 코드
            
            ```jsx
            const { data, refetch } =
              useQuery<코드젠타입>(
                GET_SOMTHING_QUERY,
                { fetchPolicy: "network-only" }
              );
            ```
            
    - skip option을 주면 해당 경우에는 새 요청 하지 않게 할 수 있음
