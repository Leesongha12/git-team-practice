# 제출물 인덱스 — Git 팀 협업 실습

## 1. 팀 정보

- 저장소: [git-team-practice](https://github.com/Leesongha12/git-team-practice)
- 팀원: 이송하(Leesongha12), 이지영(L-jy16), 황승재(bidulgiya999)
- 결과물 유형: 팀 소개 문서
- 브랜치 전략: GitHub Flow
- 개발 환경: Windows, VS Code, PowerShell, Git, GitHub
- 제출 문서 정리 Issue: [#23](https://github.com/Leesongha12/git-team-practice/issues/23)

복잡한 기능 구현보다 Issue, 브랜치, 커밋, PR, 코드 리뷰, 충돌 해결 및 트러블슈팅 기록을 중심으로 협업을 실습했다.

기본 작업 흐름:

Issue 생성 → feature 브랜치 생성 → 수정 및 커밋 → push → PR 생성 → 리뷰 및 수정 → 승인 → main 병합

## 2. 결과물과 주요 문서

| 구분 | 문서 |
| --- | --- |
| 프로젝트 소개 및 팀원 목차 | [README.md](README.md) |
| 이송하 소개 | [team/songha.md](team/songha.md) |
| 이지영 소개 | [team/jiyoung.md](team/jiyoung.md) |
| 황승재 소개 | [team/seungjae.md](team/seungjae.md) |
| 협업 규칙 | [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) |
| 충돌 해결 기록 | [docs/conflict-resolution.md](docs/conflict-resolution.md) |
| Git 트러블슈팅 기록 | [docs/troubleshooting-log.md](docs/troubleshooting-log.md) |
| Git 히스토리 증빙 | [docs/evidence/git-log-graph.txt](docs/evidence/git-log-graph.txt) |
| 전체 증빙 폴더 | [docs/evidence](docs/evidence/) |

협업 가이드에는 브랜치 네이밍, 커밋 메시지, Issue와 PR 작성, 코드 리뷰, 충돌 대응 및 공유 히스토리 보호 규칙을 정리했다.

## 3. 팀원별 Issue 및 PR

### 이송하 — Leesongha12

#### 관련 Issue

- [#1: 팀 소개](https://github.com/Leesongha12/git-team-practice/issues/1)
- [#7: 협업 가이드](https://github.com/Leesongha12/git-team-practice/issues/7)
- [#14: 첫 번째 충돌 기록](https://github.com/Leesongha12/git-team-practice/issues/14)
- [#16: 두 번째 충돌 실습](https://github.com/Leesongha12/git-team-practice/issues/16)
- [#18: Git 트러블슈팅](https://github.com/Leesongha12/git-team-practice/issues/18)
- [#23: 제출 문서 및 증빙 정리](https://github.com/Leesongha12/git-team-practice/issues/23)

#### 생성 및 병합한 PR

| PR | 작업 내용 |
| --- | --- |
| [#2](https://github.com/Leesongha12/git-team-practice/pull/2) | 본인 소개 문서 작성 및 리뷰 반영 |
| [#8](https://github.com/Leesongha12/git-team-practice/pull/8) | 협업 가이드 작성 및 리뷰 예시 보완 |
| [#15](https://github.com/Leesongha12/git-team-practice/pull/15) | 첫 번째 충돌 해결 기록 정리 |
| [#17](https://github.com/Leesongha12/git-team-practice/pull/17) | 두 번째 충돌 재현·해결 및 증빙 연결 |
| [#19](https://github.com/Leesongha12/git-team-practice/pull/19) | amend 및 soft reset 기록과 증빙 |
| [#22](https://github.com/Leesongha12/git-team-practice/pull/22) | stash 실습 및 트러블슈팅 기록 정리, 리뷰 반영 |

#### 기여 및 실습 참여

- [본인 소개 문서](team/songha.md)
- amend와 reset --soft 실행 및 기록 작성
- 충돌 해결 기록과 제출물 인덱스 정리
- 팀원이 수행한 revert 및 stash 실습 내용 문서화

### 이지영 — L-jy16

#### 관련 Issue

- [#9: 충돌 대응 규칙](https://github.com/Leesongha12/git-team-practice/issues/9)

#### 생성 및 병합한 PR

| PR | 작업 내용 |
| --- | --- |
| [#4](https://github.com/Leesongha12/git-team-practice/pull/4) | 본인 소개 문서 작성 및 학습 목표 구체화 |
| [#11](https://github.com/Leesongha12/git-team-practice/pull/11) | 충돌 발생 시 공유할 정보와 위치 구체화 |

#### 기여 및 실습 참여

- [본인 소개 문서](team/jiyoung.md)
- 첫 번째 충돌 해결 및 해결 내용 공유
- 원격에 push한 커밋의 revert 실행
- [취소 대상 커밋 ac43411](https://github.com/Leesongha12/git-team-practice/commit/ac43411)
- [취소 커밋 47a54e5](https://github.com/Leesongha12/git-team-practice/commit/47a54e5)

### 황승재 — bidulgiya999

#### 관련 Issue

- [#12: 충돌 대응 규칙](https://github.com/Leesongha12/git-team-practice/issues/12)

#### 생성 및 병합한 PR

| PR | 작업 내용 |
| --- | --- |
| [#6](https://github.com/Leesongha12/git-team-practice/pull/6) | 본인 소개 문서 작성 및 제목·형식 수정 |
| [#13](https://github.com/Leesongha12/git-team-practice/pull/13) | 충돌 대응 규칙 수정 |

#### 기여 및 실습 참여

- [본인 소개 문서](team/seungjae.md)
- 충돌 해결 담당자와 공동 확인자 지정 규칙 작성
- stash와 stash pop 실행
- 실습 기록은 [PR #22](https://github.com/Leesongha12/git-team-practice/pull/22)에 포함

PR #22는 이송하가 생성한 PR이며, 황승재의 실습 참여와 PR 작성자 실적을 구분한다.

## 4. 코드 리뷰 및 반영 증빙

### 다른 팀원의 PR에 작성한 실질 리뷰

| 리뷰 작성자 | 대상 PR | 리뷰 내용 및 직접 링크 |
| --- | --- | --- |
| 이송하 | #4 | [충돌 실습 학습 목표 구체화 제안](https://github.com/Leesongha12/git-team-practice/pull/4#discussion_r4312566743) |
| 이송하 | #6 | [Markdown 제목 공백 수정 제안](https://github.com/Leesongha12/git-team-practice/pull/6#pullrequestreview-5570391643) |
| 이지영 | #2 | [자동화 관심 분야의 구체적 예시 추가 제안](https://github.com/Leesongha12/git-team-practice/pull/2#discussion_r4312163389) |
| 이지영 | #8 | [코드 리뷰 예시 추가 제안](https://github.com/Leesongha12/git-team-practice/pull/8#discussion_r4313122424) |
| 황승재 | #17 | [충돌 원문 증빙을 상대 경로 링크로 연결하자는 제안](https://github.com/Leesongha12/git-team-practice/pull/17#discussion_r4314365989) |

황승재의 두 번째 실질 리뷰 직접 링크는 추가 확인이 필요하다. 단순 승인이나 칭찬만 있는 댓글은 실질 리뷰 실적으로 계산하지 않는다.

### 본인 PR에서 리뷰를 반영한 사례

| 작성자 | 대상 PR | 반영 내용 | 증빙 |
| --- | --- | --- | --- |
| 이송하 | #2 | AI 작업 자동화 관심 분야를 구체적인 예시로 보완 | [답변](https://github.com/Leesongha12/git-team-practice/pull/2#discussion_r4312263483), [수정 커밋 8acbeba](https://github.com/Leesongha12/git-team-practice/commit/8acbeba) |
| 이지영 | #4 | 충돌 해결 학습 목표 구체화 | [수정 커밋 2dfb7c3](https://github.com/Leesongha12/git-team-practice/commit/2dfb7c3) |
| 황승재 | #6 | 소개 문서의 제목 및 형식 수정 | [수정 커밋 d3bc197](https://github.com/Leesongha12/git-team-practice/commit/d3bc197) |

### 추가 리뷰 및 반영 사례

- [PR #11의 이송하 댓글](https://github.com/Leesongha12/git-team-practice/pull/11#issuecomment-6266241033)
- [PR #13의 이송하 리뷰](https://github.com/Leesongha12/git-team-practice/pull/13#pullrequestreview-5571500051)
- [PR #8: 코드 리뷰 예시 추가 커밋 0f2acf7](https://github.com/Leesongha12/git-team-practice/commit/0f2acf7)
- [PR #17: 충돌 원문 증빙 링크 추가 커밋 dfa9683](https://github.com/Leesongha12/git-team-practice/commit/dfa9683)
- [PR #22: stash apply와 pop 차이 설명 추가 커밋 6eb3246](https://github.com/Leesongha12/git-team-practice/commit/6eb3246)

## 5. 충돌 해결 증빙

상세한 상황, 해결 과정, 결과 및 배운 점은 [충돌 해결 기록](docs/conflict-resolution.md)에서 확인할 수 있다.

### 충돌 기록 1 — 협업 가이드의 충돌 대응 규칙 통합

- 충돌 파일: `docs/CONTRIBUTING.md`
- 작업 브랜치: `feature/seungjae-conflict-guide`
- 선행 작업: 지영의 PR #11
- 충돌이 발생한 PR: 승재의 PR #13
- 참여자:
  - 이지영: 정보 공유 규칙 작성 및 충돌 해결
  - 황승재: 해결 담당자와 공동 확인자 규칙 작성
  - 이송하: 리뷰, 병합 및 기록 문서 정리

팀원들이 같은 문서의 충돌 대응 규칙을 각각 수정했고, PR #11이 main에 먼저 병합된 뒤 PR #13에서 충돌이 발생했다.

두 변경의 목적을 비교하여 해결했으며, 해결 의도와 실제 최종 반영 내용의 차이도 충돌 기록 문서에 정리했다. 상세 해결 절차와 후속 확인 내용은 해당 문서를 기준으로 확인한다.

#### 관련 PR 및 커밋

- [선행 PR #11](https://github.com/Leesongha12/git-team-practice/pull/11)
- [충돌 발생 PR #13](https://github.com/Leesongha12/git-team-practice/pull/13)
- [충돌 해결 관련 병합 커밋 f141f28](https://github.com/Leesongha12/git-team-practice/commit/f141f28)
- [main 병합 커밋 8f85bd9](https://github.com/Leesongha12/git-team-practice/commit/8f85bd9)
- [충돌 기록 PR #15](https://github.com/Leesongha12/git-team-practice/pull/15)
- [충돌 기록 PR 병합 화면](docs/evidence/songha-pr-15-conflict-log-merged.png)

### 충돌 기록 2 — 같은 hunk의 서로 다른 변경 통합

- 관련 Issue: [#16](https://github.com/Leesongha12/git-team-practice/issues/16)
- 관련 PR: [#17](https://github.com/Leesongha12/git-team-practice/pull/17)
- 실행 및 기록 작성자: 이송하
- 충돌 파일: `docs/CONTRIBUTING.md`
- 실습 브랜치:
  - `feature/songha-conflict16-a`
  - `feature/songha-conflict16-b`

같은 파일의 같은 문장을 두 브랜치에서 서로 다르게 수정하여 비자명 충돌을 재현했다.

- A 브랜치: 충돌한 브랜치 이름과 파일 경로를 공유하도록 수정
- B 브랜치: 실행 명령어와 오류 메시지를 공유하도록 수정
- 해결 방법: 두 변경이 모두 필요하다고 판단하여 하나의 문장으로 통합
- 검증: 충돌 마커 제거 및 양쪽 정보의 보존 여부 확인

이번 사례는 한 사람이 두 브랜치를 사용한 재현 실습이며, 두 사람이 각각 수행한 작업으로 기재하지 않는다.

#### 증빙

- [충돌 발생 터미널 화면](docs/evidence/conflict-02-terminal.png)
- [충돌 마커 화면](docs/evidence/conflict-02-markers.png)
- [해결 전 충돌 마커 원문](docs/evidence/conflict-02-before.txt)
- [해결 커밋 5b3f089](https://github.com/Leesongha12/git-team-practice/commit/5b3f089)
- [증빙 링크 리뷰 반영 커밋 dfa9683](https://github.com/Leesongha12/git-team-practice/commit/dfa9683)
- [main 병합 커밋 6889ee4](https://github.com/Leesongha12/git-team-practice/commit/6889ee4)
- [PR 병합 화면](docs/evidence/conflict-02-pr-merged.png)

## 6. Git 트러블슈팅 증빙

실제 명령어, 상황, 결과, 선택 이유 및 주의점은 [Git 트러블슈팅 기록](docs/troubleshooting-log.md)에 정리했다.

### 실습별 참여 및 결과

| 시나리오 | 실제 실행자 | 결과 |
| --- | --- | --- |
| git commit --amend | 이송하 | push 전 최근 커밋의 메시지 수정 |
| git reset --soft HEAD~1 | 이송하 | 로컬 커밋을 취소하고 변경과 스테이징 상태 유지 |
| git revert | 이지영 | 원격에 push한 커밋의 변경을 새 커밋으로 취소 |
| git stash / git stash pop | 황승재 | 미커밋 변경 보관, 브랜치 전환 및 변경 복원 |

- 기록 문서 정리: 이송하
- 관련 PR: [#19](https://github.com/Leesongha12/git-team-practice/pull/19), [#22](https://github.com/Leesongha12/git-team-practice/pull/22)
- 실제 실행자와 기록 작성 역할은 구분하여 기재한다.
- 팀원별 해결 기록 작성 참여는 문서와 관련 댓글에서 확인할 수 있도록 보완한다.

### 실습 1 — amend

push하지 않은 최근 커밋의 메시지를 더 구체적으로 수정했다.

- 수정 전: `dbf4f7f`
- 수정 후: `b2018be`
- 파일 내용은 유지됐으며, 커밋이 대체되어 커밋 번호가 변경됐다.

증빙:

- [수정 전 화면](docs/evidence/songha-amend-before.png)
- [수정 후 화면](docs/evidence/songha-amend-after.png)

### 실습 2 — reset --soft

push하지 않은 최근 커밋을 취소하고 변경 내용을 유지한 뒤 다시 커밋했다.

- 취소 대상: `b2018be`
- 이동한 이전 커밋: `6889ee4`
- 재커밋: `be3db7a`
- 파일 내용과 스테이징 상태가 유지됐음을 확인했다.

증빙:

- [reset 후 변경 유지 확인](docs/evidence/songha-reset-soft-after.png)
- [reflog 및 재커밋 결과](docs/evidence/songha-troubleshooting-reflog.png)

### 실습 3 — revert

파일 추가 커밋을 원격에 push한 뒤, 해당 변경을 취소하는 새 커밋을 생성하고 push했다.

- 작업 브랜치: `feature/jiyoung-revert-practice`
- 대상 파일: `src/revert-practice.txt`
- 취소 대상: `ac43411`
- 취소 커밋: `47a54e5`
- 원래 커밋을 유지하면서 파일 추가를 되돌렸다.

증빙:

- [취소 전 커밋과 push 결과](docs/evidence/revert-before.png)
- [취소 후 검증 결과](docs/evidence/revert-after.png)
- [원래 커밋 ac43411](https://github.com/Leesongha12/git-team-practice/commit/ac43411)
- [취소 커밋 47a54e5](https://github.com/Leesongha12/git-team-practice/commit/47a54e5)

### 실습 4 — stash / stash pop

이미 추적 중인 파일의 미커밋 변경을 보관하고, 다른 브랜치로 이동했다가 돌아와 복원했다.

- 작업 브랜치: `feature/seungjae-stash-practice`
- 전환한 브랜치: `feature/jiyoung-revert-practice`
- 대상 파일: `src/stash-practice.txt`
- 보관 후 작업 트리가 깨끗한 상태임을 확인했다.
- 복원 후 추가한 문장이 다시 나타났음을 확인했다.
- 충돌 없이 pop이 성공하여 해당 stash 항목이 제거됐다.
- 리뷰를 반영하여 stash apply와 pop의 차이를 문서에 추가했다.

증빙:

- [보관 전 변경 내용](docs/evidence/stash-before.png)
- [보관 후 상태와 목록](docs/evidence/stash-saved.png)
- [브랜치 전환과 복귀](docs/evidence/stash-switch.png)
- [복원 후 변경 내용과 빈 목록](docs/evidence/stash-after.png)
- [리뷰 반영 커밋 6eb3246](https://github.com/Leesongha12/git-team-practice/commit/6eb3246)

### 명령별 차이와 사용 기준

| 명령 | 사용 목적 | 히스토리 및 작업 내용에 미치는 영향 |
| --- | --- | --- |
| amend | 최근 커밋 수정 | 최근 커밋을 새로운 커밋으로 대체 |
| reset --soft | 커밋 취소 및 변경 유지 | 브랜치가 가리키는 커밋을 옮기고 작업 트리와 인덱스 유지 |
| revert | 공유한 변경 취소 | 기존 커밋을 유지하며 반대 변경의 커밋 추가 |
| stash | 미커밋 변경 임시 보관 | 변경을 보관하고 작업 전환 준비 |
| stash pop | 보관한 변경 복원 | 성공적으로 적용하면 해당 stash 항목 제거 |
| stash apply | 보관한 변경 적용 | 적용 후에도 stash 항목 유지 |

공유한 커밋에는 팀 합의 없이 amend, rebase 또는 강제 push를 적용하지 않는다. 공유된 변경을 취소할 때는 기존 이력을 보존하는 revert를 우선 검토한다.

## 7. Git 히스토리 증빙

- [git log --oneline --graph --all 출력](docs/evidence/git-log-graph.txt)
- [amend와 reset의 로컬 실행 이력](docs/evidence/songha-troubleshooting-reflog.png)

Git 그래프는 브랜치의 분기와 병합 및 커밋 연결 관계를 보여 준다. amend와 reset으로 대체되거나 브랜치에서 벗어난 로컬 커밋은 일반 로그에 나타나지 않을 수 있으므로, 해당 실습은 reflog 화면도 함께 첨부했다.

히스토리 파일은 생성 시점의 기록이다. 제출 문서 정리 이후의 커밋이나 병합은 저장소의 최신 커밋 및 PR 기록에서 추가 확인할 수 있다.

## 8. 브랜치 보호 및 병합 증빙

### main 브랜치 보호 설정

팀의 운영 기준:

- main에 직접 push하지 않는다.
- 변경은 PR을 통해 병합한다.
- 작성자 외 팀원 최소 1명의 승인을 받는다.
- 보호 규칙을 우회하지 않고 리뷰와 검증을 거친다.

설정 증빙:

- [PR 및 리뷰 승인 설정 화면](docs/evidence/main-protection-review.png)
- [보호 규칙 우회 제한 설정 화면](docs/evidence/main-protection-no-bypass.png)

### 주요 PR 병합 및 리뷰 화면

| 구분 | 증빙 |
| --- | --- |
| 송하 소개 PR #2 | [병합 화면](docs/evidence/songha-pr-2-merged.png) |
| 지영 소개 PR #4 | [병합 화면](docs/evidence/jiyoung-pr-merged.png), [리뷰 상호작용](docs/evidence/jiyoung-review-interaction.png) |
| 승재 소개 PR #6 | [병합 화면](docs/evidence/seungjae-pr-6-merged.png), [리뷰 반영 화면](docs/evidence/seungjae-pr-6-review-feedback.png) |
| 협업 가이드 PR #8 | [병합 화면](docs/evidence/songha-pr-8-merged.png) |
| 지영 충돌 대응 PR #11 | [병합 화면](docs/evidence/jiyoung-pr-11-merged.png) |
| 승재 충돌 대응 PR #13 | [병합 화면](docs/evidence/seungjae-pr-13-merged.png) |
| 첫 번째 충돌 기록 PR #15 | [병합 화면](docs/evidence/songha-pr-15-conflict-log-merged.png) |
| 두 번째 충돌 실습 PR #17 | [병합 화면](docs/evidence/conflict-02-pr-merged.png) |

스크린샷은 촬영 시점의 상태를 보여 준다. 최신 승인 및 병합 상태는 각 PR 페이지에서 확인한다.

## 9. 제출 전 최종 확인

빈 체크박스는 미확인 또는 보완할 항목이다. 실제 기록과 파일을 확인한 뒤 완료 처리한다.

- [x] 팀원별 소개 문서 링크 정리
- [x] 협업 문서 3종 링크 정리
- [x] 팀원별 주요 Issue 및 PR 링크 정리
- [x] 충돌 해결 2건의 PR 및 커밋 링크 정리
- [x] 같은 hunk를 수정한 비자명 충돌의 원문 증빙 연결
- [x] amend, reset --soft, revert, stash/pop 실습 기록 연결
- [x] 송하와 지영의 실질 리뷰 각 2건 링크 정리
- [x] 승재의 첫 번째 실질 리뷰 및 해당 수정 커밋 연결
- [x] 각 팀원의 본인 PR 리뷰 반영 사례 연결
- [x] Git 그래프 및 로컬 reflog 증빙 연결
- [x] 제출 문서 정리 Issue #23 연결
- [ ] 제출 문서 정리 PR 링크 추가
- [ ] 승재의 두 번째 실질 리뷰와 작성자의 답변 또는 수정 반영 증빙 추가
- [ ] 각 팀원의 PR 2개 이상 생성·병합 및 리뷰 2개 이상 기준 최종 확인
- [ ] 각 PR의 실질 코멘트, 작성자와의 상호작용 및 타인 승인 확인
- [ ] 팀원별 Issue 목록 보완 및 PR 본문의 Closes/Fixes 연결 확인
- [ ] stash 실습의 실제 관련 Issue 번호를 트러블슈팅 문서에 반영
- [ ] 모든 팀원의 트러블슈팅 해결 기록 작성 참여가 이름과 역할로 드러나는지 확인
- [ ] 충돌 기록에 실제 상황·해결 절차·결과·주의점이 포함됐는지 확인
- [ ] README에서 모든 팀원 소개 문서로 이동할 수 있는지 확인
- [ ] 증빙 사진이 docs/evidence에 커밋되어 있고 파일명·확장자가 링크와 일치하는지 확인
- [ ] main 브랜치 보호 규칙이 실제 적용되어 있는지 확인
- [ ] Git 히스토리 파일이 정상적으로 열리고 한글이 깨지지 않는지 확인
- [ ] 모든 상대 경로 링크와 GitHub 증빙 링크 확인
- [ ] 최종 제출 PR의 리뷰 및 승인 후 main 병합