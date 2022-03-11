# Git branch

- `git branch` : 브랜치 목록 확인
- `git branch 브랜치명` : 새로운 브랜치 생성
- `git branch -d 브랜치명` : 특정 브랜치(병합된 브랜치) 삭제
- `git branch -D 브랜치명` : 특정 브랜치 강제 삭제
- `git switch 브랜치명` : 브랜치 이동
- `git switch -c 브랜치명` : 브랜치를 새로 생성과 동시에 이동
- git log --oneline --all --graph



## merge(병합)

- `git merge 브랜치명` : merge 전 해당 브랜치를 합치려는 메인 브랜치로 switch해야 함

- fast-forward
  - 새로운 버전 생기지 않음
- 3-way merge(merge commit)
  - 새로운 버전 생김
- merge conflict
  - merge하는 두 브랜치에서 같은 파일의 같은 부분을 동시에 수정하고 merge하면 git은 해당 부분을 자동으로 merge 해주지 못함
  - 반면 동일 파일이라도 서로 다른 부분을 수정했다면 conflict 없이 자동으로 merge commit 됨
  - conflict 해결 후 commit 메시지 없이 그냥 commit만
