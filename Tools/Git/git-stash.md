## git stash 명령어 모음

하던 작업을 커밋 안 한 채로 남겨두고 브랜치 바꾸고 싶을 때 쓰는 명령어!

- `git stash`: 하던 작업 임시 저장 (스택에 stash 만들기)
- `git stash list`: stash 목록 확인
- `git stash apply`: 스택 최상단에 stash한 내용 적용
- `git stash apply stash@{번호}`: stash@{번호}에 stash한 내용 적용
- `git stash drop`: 스택 최상단의 stash 제거
- `git stash drop stash@{번호}`: stash@{번호} stash 제거
- `git stash pop`: apply && drop
- `git stash show -p | git apply -R`: stash 적용 이전 상태로 돌리기
- `git stash push --staged`: staging(git add)된 파일만 stash에 저장
