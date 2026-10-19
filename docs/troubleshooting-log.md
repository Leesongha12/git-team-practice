# Git Troubleshooting Log

## 실습 1: amend로 최근 커밋 메시지 수정

### 참여자
- 실행 및 기록 작성: 이송하(Leesongha12)

### 환경과 관련 작업
- 환경: Windows, VS Code, PowerShell
- 작업 브랜치: `feature/songha-git-troubleshooting`
- 관련 Issue: https://github.com/Leesongha12/git-team-practice/issues/18
- 실습 파일: `src/songha-git-practice.txt`

### 상황
실습 파일을 로컬에서 커밋한 뒤, 커밋 메시지에 실습 종류를 더 구체적으로 표시하고자 했다.
해당 커밋은 아직 원격에 push하지 않은 상태였다.

실습 파일 내용:

```text
이송하의 Git amend와 reset --soft 실습 파일입니다.
```

### 실행 절차
파일을 생성하고 저장한 뒤 최초 커밋을 만들었다.

```powershell
git add src/songha-git-practice.txt
git commit -m "docs: 송하 Git 실습 파일 추가"
git --no-pager log -1 --oneline
```

이후 최근 커밋의 메시지를 수정했다.

```powershell
git commit --amend -m "docs: 송하 amend 및 soft reset 실습 파일 추가"
git --no-pager log -1 --oneline
git status
```

### 결과
- 수정 전 커밋: `dbf4f7f`
- 수정 전 메시지: `docs: 송하 Git 실습 파일 추가`
- 수정 후 커밋: `b2018be`
- 수정 후 메시지: `docs: 송하 amend 및 soft reset 실습 파일 추가`
- 파일 내용은 유지하고 커밋 메시지를 변경했다.
- 실행 후 `nothing to commit, working tree clean`을 확인했다.

### 선택 이유와 주의점
최근 커밋의 메시지를 수정하려는 목적이므로 amend를 사용했다.
amend는 기존 커밋을 새로운 커밋으로 대체하므로 커밋 번호가 바뀐다.
이번에는 push 전의 개인 작업 브랜치에서만 수행했다.
이미 공유한 커밋에는 팀 합의 없이 적용하지 않는다.

### 증빙
- [수정 전 화면](evidence/songha-amend-before.png)
- [수정 후 화면](evidence/songha-amend-after.png)
- [amend와 reset 실행 이력](evidence/songha-troubleshooting-reflog.png)

## 실습 2: reset --soft로 로컬 커밋 취소 및 변경 유지

### 참여자
- 실행 및 기록 작성: 이송하(Leesongha12)

### 관련 작업
- 관련 Issue: https://github.com/Leesongha12/git-team-practice/issues/18
- 작업 브랜치: `feature/songha-git-troubleshooting`
- 대상 커밋: `b2018be`
- 실습 파일: `src/songha-git-practice.txt`

### 상황
아직 push하지 않은 최근 커밋을 취소하되, 작성한 파일 내용은 유지하고 다시 커밋하는 상황을 실습했다.
시작 시 작업 트리는 깨끗한 상태였다.

### 실행 절차
최근 커밋을 한 단계 취소하고 스테이징 상태를 확인했다.

```powershell
git reset --soft HEAD~1
git status
git --no-pager diff --cached
```

커밋 위치와 로컬 실행 이력도 확인했다.

```powershell
git --no-pager log -1 --oneline
git --no-pager reflog -4
```

유지된 변경 내용을 다시 커밋했다.

```powershell
git commit -m "docs: soft reset 후 송하 실습 파일 다시 커밋"
git status
```

### 결과
- 현재 브랜치가 가리키는 커밋이 `b2018be`에서 이전 커밋 `6889ee4`로 이동했다.
- `src/songha-git-practice.txt`가 `Changes to be committed`에 새 파일로 표시됐다.
- `git diff --cached`에서 작성한 한 줄이 유지된 것을 확인했다.
- reflog에서 `reset: moving to HEAD~1`을 확인했다.
- 다시 생성한 커밋: `be3db7a`
- 재커밋 후 `nothing to commit, working tree clean`을 확인했다.

### 선택 이유와 주의점
커밋만 취소하고 파일 내용과 스테이징 상태를 유지하려고 `--soft`를 사용했다.
`--hard`는 작업 내용까지 잃을 수 있으므로 이번 목적에 맞지 않는다.
공유된 변경을 취소할 때는 기존 이력을 유지하는 revert를 우선 검토한다.
이번 reset은 push 전의 개인 작업 브랜치에서 한 번만 실행했으며 main은 변경하지 않았다.

### 증빙
- [reset 후 변경 유지 확인](evidence/songha-reset-soft-after.png)
- [실행 이력과 재커밋 결과](evidence/songha-troubleshooting-reflog.png)