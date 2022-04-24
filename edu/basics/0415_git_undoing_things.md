# Git Undoing Things

## 파일 내용을 수정 전으로 되돌리기

- `$ git restore <파일명>`
  - 버전 관리가 되고 있는 파일만 되돌리기 가능
  - 원래 파일로 덮어쓰기 때문에 수정한 내용은 전부 사라짐(복원 불가능)



## 파일 상태를 Unstage로 되돌리기

- `$ git rm --cached <파일명>`
  - Staging Area에 올라간 파일 다시 내리기
  - 기존에 커밋이 없는 경우 사용
- `$ git restore --staged`
  - 기존 커밋이 존재하는 경우 사용



## 바로 직전 완료한 커밋 수정하기

- `$ git commit --amend`
  - 커밋 메시지만 수정
    - 마지막 커밋 후 수정한 내용이 없을 때
  - 이전 커밋 덮어쓰기
    - Staging Area에 새로 올라온 내용이 있을 때
  - vim 에디터에서 `I`로 메시지 수정 후 `ESC`, `:wq`로 나가기
  - 새 커밋으로 분리하지 않고 하나의 커밋에서 처리
  - 이전 커밋을 지우고 새로운 커밋으로 변경하므로 주의
    - 커밋 해시 값도 변경됨
    - 히스토리에 남지 않음



## reset & revert

- `$ git reset [옵션] <커밋 ID>`
  - 특정 커밋 상태로 되돌아가기
  - 해당 커밋 이후의 커밋들은 모두 사라짐
  - 옵션
    - `--soft`
      - 이후의 커밋된 파일들을 staging area로 돌려 놓음(commit 전 상태)
    - `--mixed`
      - 이후의 커밋된 파일들을 working directory로 돌려 놓음(add 전 상태)
      - 기본값
    - `--hard`
      - 이후 커밋된(tracked) 파일들은 모두 working directory에서 삭제
      - untracked 파일들은 그대로 남음
  - `$ git reflog`
    - HEAD가 이전에 가리켰던 모든 커밋을 보여주는 명령어
    - --hard 옵션으로 지워진 커밋도 복구 가능
      - `$ git reflog`로 커밋 해시 확인 후 `$ git reset --hard <커밋 ID>`
- `$ git revert <커밋 ID>`
  - 이전 커밋을 취소한다는 새로운 커밋 생성
  - 파일 상태는 되돌아가나 히스토리는 유지
