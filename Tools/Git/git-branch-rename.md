# 브랜치 이름 변경하기

- 현재 브랜치 이름 변경: `git branch -m 바꿀브랜치명`
- 다른 브랜치 이름 변경: `git branch -m 이전브랜치명 바꿀브랜치명`
- 푸시한 경우 `git push origin :이전브랜치명` 으로 이전 브랜치 제거하면 정상적으로 지워짐. 바꾼 브랜치명으로 새로 푸시하면 됨.