## 문제 상황

ssh 설정하고 깃크라켄이 ssh remote를 인식 못해서 https로 바꿔줌

그랬더니 pr 날린 후 vercel 배포가 자동으로 안 됨

> Someone is attempting to deploy this pull request to the Team on [Vercel](https://vercel.com/).
> 
> 
> To accomplish this, the commit author's email address needs to be associated with a GitHub account.
> 
> [Learn more](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address#setting-your-commit-email-address-in-git) about how to change the commit author information.
> 

계정 설정이 잘못된 것으로 짐작돼 git config user.name으로 확인해봤더니 내 username도 email 주소로 돼있었음. 

## 해결 방법

git config [user.name](http://user.name) seohyunPang 으로 user.name 다시 설정

git commit --amend --author="seohyunPang”으로 계정 설정

git reset --soft HEAD~1
