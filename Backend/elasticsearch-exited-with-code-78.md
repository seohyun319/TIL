### 문제 상황
docker 켤 때 `elastic search exited with code 78`과 함께 elastic search가 작동 안 함

### 에러 원인

엘라스틱 서치 용량이 너무 커서 뱉어내고 있는 것

### 해결 방법

`sudo sysctl -w vm.max_map_count=262144` 명령어로 최대 용량을 키워준다.
터미널에서 sudo 명령어를 인식을 못해서 wsl을 관리자권한으로 열어준 후 sudo를 뺀 나머지 명령어를 입력했다.
