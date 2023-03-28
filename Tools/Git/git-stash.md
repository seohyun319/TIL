## git stash 명령어 모음

하던 작업을 커밋 안 한 채로 남겨두고 브랜치 바꾸고 싶을 때 쓰는 명령어!

- `git stash`: 하던 작업 임시 저장 (스택에 stash 만들기)
- `git stash list`: stash 목록 확인
- `git stash apply`: 스택 최상단에 stash한 내용 적용
- `git stash apply stash@{번호}`: stash@{번호}에 stash한 내용 적용
- `git stash drop`: 스택 최상단의 stash 제거
- `git stash drop stash@{번호}`: stash@{번호} stash 제거
- `git stash pop`: apply && drop
- `git stash show`: stash한 내용 간략히 보기 (어떤 파일이 변경됐는지 등)
- `git stash show -p`: stash한 내용 자세히 보기 (변경 내용)
- `git stash show stash@{번호} -p`: stash@{번호}에서 stash한 내용 자세히 보기
- `git stash show -p | git apply -R`: stash 적용 이전 상태로 돌리기 (Reverse, rollback)
- `git stash push --staged`: staging(git add)된 파일만 stash에 저장
