## merge
병합 실행하고 새로운 커밋 이력 생성
  1. fast-forward
      - 현재 브랜치의 가장 최근 commit으로 master branch의 Head를 옮기는 것. rebase
  2. 3-way merge
      - 공통 조상으로 하는 브랜치(Main)에 새로운 commit을 만들어서 병합. 일반적인 merge 방식.

## rebase
특정 브랜치를 base로 커밋 이력 재정렬
  - 재정렬되는 commit 이력에는 이전과는 다른 새로운 해시 ID 부여
  - master 브랜치에서 다른 브랜치를 기준으로 rebase하면 master의 커밋이력이 변하기에 master에서는 피하는 게 좋음
  - 커밋 이력을 깔끔하게 관리할 때 사용
  - 언제 merge됐는지는 알 수 없음. (merge 이력이 생기지 않음)
  - sub 브랜치에서 작업 → `git checkout sub`인상태에서 `git rebase master`를 하면 master 기준으로 sub 브랜치의 이력들이 정리됨.
  - → `git checkout master` 해서 `git merge sub`로 최종 내역을 master 브랜치에 반영해야 동기화 완료됨 : merge하면 해당 브랜치 내용 그냥 머지되니까 참고하기…
  - push 전의 커밋 작업을 rebase해야. push 후에 reabse하면 꼬여서 force push 해야 함. push했으면 rebase 하지 말기.

## squash
sub 브랜치의 여러 커밋 이력을 하나의 커밋으로 합쳐 master로 합침.
  - merge 이력 생기지 않음.
  - rebase는 커밋 이력 각각이 살아있으나 squash의 경우 하나로 합쳐짐
    
---


rebase [참고 링크](https://dongminyoon.tistory.com/9)
