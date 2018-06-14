<!-- TITLE: Git -->
<!-- SUBTITLE: A quick summary of Git -->

# Git
* master : 제품으로 출시될 수 있는 브랜치
* develop : 다음 출시 버전을 개발하는 브랜치
* feature : 기능을 개발하는 브랜치
* release : 이번 출시 버전을 준비하는 브랜치
* hotfix : 출시 버전에서 발생한 버그를 수정 하는 브랜치

![Git Flow Overall Graph](/uploads/git-flow-overall-graph.png "Git Flow Overall Graph")
## PUSH
git add .
git commit -m 'message'
git push origin master

## PULL
git pull origin master

## 환경파일 삭제
.gitignore 에 환경파일 경로 추가 시, 이미 캐시된 것은 삭제해야 반영됨.
`git rm --cached`


# References
- http://woowabros.github.io/experience/2017/10/30/baemin-mobile-git-branch-strategy.html