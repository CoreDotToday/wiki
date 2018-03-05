<!-- TITLE: Git -->
<!-- SUBTITLE: A quick summary of Git -->

# Git
## PUSH
> git add .
git commit -m 'message'
git push origin master

## PULL
> git pull origin master

## 환경파일 삭제
.gitignore 에 환경파일 경로 추가 시, 이미 캐시된 것은 삭제해야 반영됨.
`git rm --cached`