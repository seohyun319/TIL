### 🗂 yarn.lock, package-lock.json, package.json 전부 깃허브에 업로드하는 것이 좋음.

next.js 공부를 하다가 yarn.lock 파일을 .gitignore에 넣어도 인식이 안 되길래 찾아보니 yarn.lock는 깃허브에 올려서 버전 관리를 하는 것이 좋다고 한다!

package-lock.json을 깃허브에 올려놓고 팀프로젝트를 진행했을 때 버전 충돌이 발생해서 그 이후 프로젝트에서는 .gitignore에 넣어놨었다. 
초기 세팅에서 필요한 패키지를 다 설치하고 시작하지 않아서 각자 필요한 거를 그때마다 설치하다보니, 똑같은 거를 각자 설치해서 충돌이 났던 것 같다. 
package-lock.json이 용량이 비교적 크기도 하고 package.json에 어차피 다 있는 정보니까 npm install을 통해 잘 될 거라 생각해서이기도 하다. 
그런데 package.json은 버전이 variation으로 있어 하나가 명시가 안 된 경우도 있다고 한다. 앞으로는 다 깃허브에 올려야지...
