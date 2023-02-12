git rebase `-i`의 i는 --interactive의 약자. git rebase 명령어를 대화형으로 실행하겠다는 의미. 

- `git rebase -i 수정할 커밋의 직전 커밋` 혹은 `git rebase -i 브랜치명`
    - 텍스트 에디터 열리고, 커밋들 표시됨
        - 수정할 커밋 ~ 현재 커밋 범위의 커밋 표시됨
            - ex) git rebase -i HEAD~3을 실행하면
            → HEAD~2 , HEAD~1, HEAD 커밋들이 출력
            
            ```
            pick 9a54fd4 commit의 설명 추가
            pick 0d4a808 pull 설명을 추가
            
            # Rebase 326fc9f..0d4a808 onto d286baa
            #
            # Commands:
            #  p, pick = use commit
            #  r, reword = use commit, but edit the commit message
            #  e, edit = use commit, but stop for amending
            #  s, squash = use commit, but meld into previous commit
            #  f, fixup = like "squash", but discard this commit's log message
            #  x, exec = run command (the rest of the line) using shell
            #
            # If you remove a line here THAT COMMIT WILL BE LOST.
            # However, if you remove everything, the rebase will be aborted.
            ```
            
    - 각 명령어 (수정 시 커밋 해시값도 같이 변경됨)
        - `pick`: 커밋을 사용하겠다 → 커밋 순서 바꾸기 등 가능
            - 원하지 않는 커밋까지 같이 올라가는 상황이면 올리고 싶은 커밋을 맨 위로 올리고 :wq로 반영
        - `reword`: 커밋 메시지 변경
            - 원하는 커밋의 pick을 reward로 바꾸고 저장하면 해당 커밋명 다시 작성하는 에디터 창 열림
        - `edit`: 커밋 메시지뿐만 아니라 작업 내용 변경
            - 변경할 커밋으로 체크아웃되기에 그 상태에서 변경할 작업 수행하면 됨.
            - `git add .` 후 `git commit --amend`로 변경 내용 저장
            - `git rebase --continue`로 rebase 마침
        - `squash`: 이전 커밋과 합침
        - `fixup`: 이전 커밋과 합치는데 커밋 메시지는 합치지 않음 (이전 커밋은 메시지만 남음)
        - `exec`: 각 커밋이 적용된 후 실행할 shell 명령어 지정 가능
            - git rev-parse HEAD 실행 시 HEAD가 가리키고 있는 커밋의 해시값 출력해줌
        - `drop`: 커밋 히스토리에서 해당 커밋 삭제. (rebase 리스트에서 해당 커밋 줄 지워도 똑같음)

<br /><br /><br />

실제 사용한 상황: release 브랜치에 원하지 않는 커밋까지 같이 올라간 상황. `git rebase -i release`, `git reset —hard 수정한커밋해시번호`로 해결하고 force push함

- git rebase -i release
    - 나오는 창에서 원하는 커밋을 맨 위로 올리고 :wq로 반영
    - Successfully rebased and updated refs/heads/브랜치명
- git log --oneline으로 확인
- git reset --hard 5e1d17eed
    - 변경 적용할 커밋 해시번호
    - HEAD의 현재 위치는 5e1d17eed입니다
- git log --oneline으로 head가 release 바로 위에 있는지 확인 (release의 가장 마지막 커밋 바로 다음에 새 커밋(HEAD)를 추가한 상태)
- git push -f로 반영

---

참고

[rebase -i 로 커밋 수정하기](https://backlog.com/git-tutorial/kr/stepup/stepup7_6.html)

[git rebase -i 알아보기](https://beomseok95.tistory.com/231)
