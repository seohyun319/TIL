`graphql-code-generator` 사용시 서버와 클라이언트 간 타입 중복 타이핑으로 인한 문제점 해결 가능

핵심 콘셉트

- code generator가 GraphQL Endpoint에 접속하여 서버 측 스키마를 다운로드 받음.
- 해당 스키마를 기반으로 타입스크립트 타입 코드를 자동으로 생성.
- 자동으로 생성된 타입을 사용하여 실제 코드에 타입을 입힘.

명령어: `yarn gql:codegen`

쿼리문 요청 후 codegen 하면 해당 요청에 맞는 타입 자동 생성해줌

[참고 링크](https://saengmotmi.netlify.app/graphql/graphql-code-generator/)
