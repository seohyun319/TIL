### 도커 명령어

개발 시작할 때: `docker-compose up --build`  
개발 끝났을 때: `docker-compose down`

- 개발 시작 전에 브랜치 바꾸고 도커 켜기
- 커밋 전에 도커 끄기 (껐다가 켜서 잘 되는지 확인하고 다시 끄는 거 권장)
- 로딩 시간 기다리기 힘들면 푸시 전이나 풀 받은 후 빼고는 --build 옵션은 빼고 up만 해도 된다.

로그 없이 백그라운드에서 돌릴 때 -d 추가: `docker-compose up -d --build`  
로그 보고 싶을 때: `docker logs -f 원하는거` (docker logs -f server)
떠있는 컨테이너 볼 때: `docker ps`
