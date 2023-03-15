- 클라이언트에서 자기에 필요한 데이터만을 쿼리할 수 있도록 함. 클라이언트가 자신에게 필요한 데이터에 대한 Query를 선언해 GraphQL에 넘기면 GraphQL은 Query를 해석해 서버에서 필요한 데이터를 가져온 후 클라이언트에 해당 쿼리에 대한 데이터를 반환
- 구조: 서버, 클라 사이에 graphQL이라는 Service Broker 레이어가 절차적으로 처리 수행. 클라는 서버 알 필요 없음. 클라에서 데이터를 조합하던 역할이 GraphQL로 옮겨지는 것
- 장점: 유지 보수 및 확장이 용이한 API 구현 가능, 이로 인해 이중 삼중으로 작업해야 하는 부분이 줄어듦. 서버에서 할 수 있는 일을 스키마 단위로 파악 가능. 필요한 정보를 유연하게 가져옴 가능. 여러번 요청하는 것을 한 번으로 줄임으로써 서버의 리소스를 최적, 클라이언트의 요청에 대한 부담이 줄어듦.
- 단점: 통신 로직 구현 편해지지만 서버에서의 일 가중
- 메서드: 데이터 읽기R는 query, 데이터를 변화 시킨(CUD) 후 응답은 mutation, 데이터 구독(실시간 변경 데이터 가져옴)은 subscription
- GraphQL(쿼리언어)을 활용 할 수 있게 도와주는 다양한 라이브러리: [릴레이(Relay)](https://relay.dev/), [아폴로(Apollo GraphQL)](https://www.apollographql.com/)
- [출처](https://kotlinworld.com/m/330)