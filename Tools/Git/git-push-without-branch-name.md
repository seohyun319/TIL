## git push 브랜치명 입력 안 하기

`git config --global push.default current`

설정 시 upstream 브랜치를 따로 지정하지 않아도 되는 대신 로컬 브랜치와 리모트 브랜치는 서로 추적이 되지 않는 상태가 됨 → git pull 시 에러 → `git push -u`를 사용해 upstream 정보를 생성해주면 git pull이 정상 작동

[Git branch의 push, --set-upstream 설정 생략하기](https://codeac.tistory.com/120)
