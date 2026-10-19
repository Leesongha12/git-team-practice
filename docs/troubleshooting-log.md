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

## 실습 3: 원격에 push한 커밋을 git revert로 취소

### 참여자
- 실제 실행자: <이지영>
- 기록 작성자: <이송하>

### 상황
원격에 push한 파일 추가 커밋을 취소하는 상황을 실습했다.
작업 브랜치는 `feature/jiyoung-revert-practice`이며,
취소 대상 파일은 `src/revert-practice.txt`다.

### 실행 과정

1. 실습용 파일을 생성하고 다음 명령으로 커밋했다.

```powershell
git add src/revert-practice.txt
git commit -m "docs: revert 취소 대상 실습 파일 추가"
```

생성된 커밋은 `ac43411`이다.

2. 해당 커밋을 원격 브랜치에 push했다.

```powershell
git push -u origin feature/jiyoung-revert-practice
```

3. 원격에 공유한 커밋의 변경을 revert로 취소했다.

```powershell
git revert --no-edit ac43411
```

취소 커밋 `47a54e5`가 생성됐으며,
파일 추가를 되돌려 `src/revert-practice.txt`가 삭제됐다.

4. 취소 커밋을 원격 브랜치에 push했다.

```powershell
git push
```

### 결과
- 원래 커밋 `ac43411`을 삭제하지 않고 유지했다.
- 변경을 취소하는 새 커밋 `47a54e5`를 생성했다.
- 실습 파일의 추가가 취소됐다.
- 원격 브랜치에 취소 커밋을 반영했다.

### 검증 방법

```powershell
git --no-pager log -2 --oneline
git status
Test-Path src/revert-practice.txt
```

검증 기준:
- 로그에 원래 커밋과 취소 커밋이 모두 나타난다.
- 작업 디렉터리가 clean 상태다.
- 파일 존재 확인 결과가 `False`다.

### 이 방법을 선택한 이유
이미 원격에 공유한 커밋이므로 기존 히스토리를 유지하는 revert를 사용했다.
reset으로 브랜치를 과거로 옮기고 강제로 push하는 방식 대신,
취소 내역을 새 커밋으로 남겨 팀원이 변경 과정을 확인할 수 있게 했다.

### 주의점
- 이번 실습은 일반 커밋 하나를 취소한 사례다.
- revert는 기존 커밋을 삭제하지 않고 변경을 되돌리는 커밋을 만든다.
- 이후 변경과 겹치는 경우 revert 중에도 충돌이 발생할 수 있다.
- 공유 브랜치의 히스토리를 강제로 변경하지 않는다.

### 증빙
- [취소 전 커밋과 push 결과](evidence/revert-before.png)
- [취소 후 검증 결과](evidence/revert-after.png)
- [취소 대상 커밋 ac43411](https://github.com/Leesongha12/git-team-practice/commit/ac43411)
- [취소 커밋 47a54e5](https://github.com/Leesongha12/git-team-practice/commit/47a54e5)


## 실습 4: stash와 stash pop으로 작업 보관 및 복원

### 참여자
- 실제 실행자: <황승재>
- 기록 작성자: <이송하>

### 환경과 관련 작업
- 환경: Windows, VS Code, PowerShell
- 관련 Issue: #<생성한 Issue 번호>
- 작업 브랜치: `feature/seungjae-stash-practice`
- 전환한 브랜치: `feature/jiyoung-revert-practice`
- 실습 파일: `src/stash-practice.txt`

### 상황
이미 커밋한 실습 파일에 두 번째 문장을 추가하던 중,
다른 브랜치로 이동해야 하는 상황을 실습했다.
아직 커밋하지 않은 변경을 stash로 보관하고 돌아와 복원했다.

### 실습 파일 내용

최초 커밋한 내용:

```text
stash 실습의 기본 내용입니다.
```

커밋하지 않고 추가한 내용:

```text
아직 커밋하지 않은 작업을 잠시 보관합니다.
```

### 실행 절차

1. 기본 파일을 생성하고 Git이 추적하도록 커밋했다.

```powershell
git add src/stash-practice.txt
git commit -m "docs: stash 실습용 기본 파일 추가"
```

2. 두 번째 문장을 추가하고 저장한 뒤 변경 내용을 확인했다.

```powershell
git status
git --no-pager diff -- src/stash-practice.txt
```

3. 해당 파일의 변경을 임시 보관했다.

```powershell
git stash push -m "작업 전환 실습" -- src/stash-practice.txt
git status
git stash list
```

4. 다른 브랜치로 전환했다가 원래 실습 브랜치로 돌아왔다.

```powershell
git switch feature/jiyoung-revert-practice
git branch --show-current
git switch feature/seungjae-stash-practice
git branch --show-current
```

5. 보관한 변경을 복원하고 결과를 확인했다.

```powershell
git stash pop
git --no-pager diff -- src/stash-practice.txt
git status
git stash list
```

### 결과
- stash 후 `nothing to commit, working tree clean`을 확인했다.
- stash 목록에 `작업 전환 실습` 항목이 생성됐다.
- 다른 브랜치로 전환했다가 실습 브랜치로 복귀했다.
- stash pop 후 추가했던 두 번째 문장이 복원됐다.
- 파일은 커밋 전 변경 상태인 `modified`로 표시됐다.
- `Dropped refs/stash@{0}` 메시지를 확인했다.
- 마지막 `git stash list` 결과는 비어 있었다.
- 복원 과정에서 충돌은 발생하지 않았다.

### 이 방법을 선택한 이유
완성되지 않은 변경을 임시 커밋하지 않고 보관한 뒤,
다른 브랜치에서 작업하고 돌아와 이어서 작업하기 위해 stash를 사용했다.
이번에는 파일 경로를 지정해 실습 파일의 변경만 보관했다.

### 주의점
- 기본 stash는 추적되지 않는 새 파일을 포함하지 않으므로 이미 커밋한 파일을 수정했다.
- stash는 로컬에 보관되며 일반적인 git push로 공유되지 않는다.
- stash pop은 변경을 복원하며, 성공하면 해당 보관 항목을 제거한다.
- 복원 중 충돌이 발생하면 stash 항목이 남을 수 있으므로 상태와 목록을 확인한다.
- 복원된 변경은 자동으로 커밋되지 않으므로 별도로 커밋해야 한다.
- git stash apply는 변경을 복원한 뒤에도 stash 항목을 유지하므로, 같은 변경을 다시 적용하거나 보관본을 남겨두려는 경우 사용할 수 있다.

### 증빙
- [보관 전 변경 내용](evidence/stash-before.png)
- [보관 후 상태와 목록](evidence/stash-saved.png)
- [브랜치 전환과 복귀](evidence/stash-switch.png)
- [복원 후 변경 내용과 빈 목록](evidence/stash-after.png)