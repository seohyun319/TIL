- 깃허브에 푸시, 풀 할 때 항상 똑같은 문장을 일일이 입력하는 것이 비효율적이라 생각해 단축어를 찾아봄
- 입력하다가 오타 나서 시간을 허비하는 것보다 그 시간에 코드 한 줄 더 고민하는 게 나은 것 같다

### 방법

터미널에 `vi ~/.gitconfig`
입력해 gitconfig 파일에 들어가서 수정. 리눅스 다루는 방식으로 수정하면 됨.

```
[alias]
    st = status
    co = checkout
    br = branch
    cm = commit -m
    ad = add .
    pl = pull
    ps = push
    plo = pull origin
    pso = push origin
    plomi = pull origin main
    psomi = push origin main
    ploms = pull origin master
    psoms = push origin master
    rs = reset HEAD^
```

나는 저렇게 지정해놨다!
<br />
이제 git plomi하면 git push origin main으로 인식된다!
