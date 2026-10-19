# 충돌 해결 기록

## 충돌 기록 #1: 협업 가이드 수정 중 발생한 충돌

### 참여자

- 이지영(L-jy16): 충돌 정보 공유 규칙 보완, 병합 커밋 f141f28의 작성자로 표시
- 황승재(bidulgiya999): feature/seungjae-conflict-guide에서 협업 가이드 수정
- 이송하(Leesongha12): PR 리뷰, 최종 main 병합, 기록 문서 정리

### 상황

팀원들이 docs/CONTRIBUTING.md의 충돌 대응 규칙을 각각 보완했다.

지영의 PR #11이 main에 먼저 병합된 후, 승재의 PR #13을 통합하는 과정에서 충돌 해결이 필요했다. 전달받은 충돌 화면에는 다음 경고와 파일 경로가 표시되어 있다.

```text
This branch has conflicts that must be resolved.
docs/CONTRIBUTING.md
```

이 상태에서는 GitHub의 Merge pull request 버튼이 비활성화되어 병합을 진행할 수 없었다.

다만 충돌 화면 캡처에는 PR 번호와 브랜치명이 포함되어 있지 않으므로, 해당 화면이 PR #13의 화면인지 작업자의 최종 확인이 필요하다.

### 관련 브랜치와 변경 목적

- main: 먼저 검토·병합된 팀의 공통 문서
- feature/jiyoung-conflict-guide: 충돌 발생 시 공유할 정보와 공유 위치 보완
- feature/seungjae-conflict-guide: 충돌 해결 담당자와 공동 확인자 규칙 보완

실습에서는 같은 항목을 서로 다르게 수정하도록 작업을 나눴다. 정확히 충돌한 문장과 범위는 당시 파일 또는 커밋 비교를 통해 보완한다.

### 충돌 마커의 의미

아래는 충돌 마커의 구조를 설명하기 위한 예시이며, 이번 충돌 파일의 원문은 아니다.

```text
<<<<<<< HEAD
현재 작업 브랜치의 내용
=======
병합하려는 브랜치의 내용
>>>>>>> origin/main
```

- `<<<<<<< HEAD`: 현재 체크아웃한 브랜치의 변경 내용 시작
- `=======`: 두 브랜치 내용의 구분선
- `>>>>>>> origin/main`: 가져오는 브랜치의 내용 끝

해결할 때는 양쪽의 수정 의도를 확인하여 최종 문장을 정하고, 충돌 마커를 제거해야 한다.

### 해결을 위해 제공받은 안내

VS Code에서 작업 브랜치에 최신 main을 병합하고, 충돌 파일을 수정한 다음 커밋·push하는 방법을 안내받았다.

안내된 주요 명령어는 다음과 같다.

```powershell
git status
git fetch origin
git merge origin/main
```

파일을 수정하고 저장한 뒤 수행하도록 안내된 명령어는 다음과 같다.

```powershell
git add docs/CONTRIBUTING.md
git commit -m "docs: 협업 가이드 병합 충돌 해결"
git push
```

위 명령어는 제공받은 해결 안내이며, 실제 실행 내역이 확인된 것은 아니다.
원래 안내문에는 feature/jiyoung-conflict-guide가 기재되어 있지만,
PR #13에서 확인된 작업 브랜치는 feature/seungjae-conflict-guide다.

### 해결 전략

리뷰에서는 다음 두 목적을 모두 보존하도록 요청했다.

1. 충돌 발생 시 브랜치 이름, 파일 경로, 실행한 명령어, 오류 메시지를 공유한다.
2. 충돌 해결 담당자와 공동 확인자를 지정한다.

정보 공유 규칙과 역할 분담 규칙은 서로 보완적인 내용이므로, 한쪽을 무조건 삭제하기보다 두 목적을 함께 유지하는 방향을 제안했다.

실제 최종 문장과 선택한 해결 방식은 작업자 확인 후 아래에 기록한다.

### 확인된 결과

- 지영의 PR #11이 main에 병합됐다.
  - 병합 커밋: b887a6f
- 승재의 PR #13에는 다음 두 커밋이 표시된다.
  - efc0f04: 협업 가이드 수정
  - f141f28: main을 feature/seungjae-conflict-guide에 병합
- f141f28의 작성자는 L-jy16으로 표시된다.
- PR #13은 리뷰 승인 후 main에 병합됐다.
  - 최종 병합 커밋: 8f85bd9

### 작업자 확인 및 보완

- 실제 충돌 해결자:이지영(L-jy16)
- 충돌 화면이 표시된 PR 번호:
- 사용 도구(VS Code 또는 GitHub 웹):
- 실제 수행한 명령어 또는 웹 화면 조작 순서:
- 충돌한 두 문장의 원문 또는 이를 확인할 증빙:
- 최종 반영한 문장:
- 해당 문장을 선택한 이유:
- 충돌 마커 제거 및 Markdown 표시 확인 결과:

### 관련 PR 및 증빙

- PR #11: https://github.com/Leesongha12/git-team-practice/pull/11
- PR #13: https://github.com/Leesongha12/git-team-practice/pull/13
- PR #13 커밋 목록: https://github.com/Leesongha12/git-team-practice/pull/13/commits
- 내부 병합 커밋: https://github.com/Leesongha12/git-team-practice/commit/f141f28
- 충돌 발생 화면: image(20261019-120324).png
- 병합 기록 화면: seungjae-pr-13-merge-history.png

증빙 이미지는 저장소에 추가한 뒤 실제 파일 경로로 연결한다.

### 배운 점과 주의점

- 다른 팀원의 변경이 main에 먼저 반영되면 작업 브랜치와 충돌할 수 있다.
- 충돌 해결은 어느 한쪽을 무조건 선택하는 작업이 아니라, 각 변경의 목적에 맞게 최종 내용을 정하는 작업이다.
- Approve는 리뷰 승인, Resolve conversation은 리뷰 대화 종료이며 파일 충돌 해결과는 다르다.
- 해결 명령어 안내와 실제 수행 기록을 구분해야 재현 가능한 문서를 남길 수 있다.
- 다음 실습부터는 충돌 원문, 해결 전후 내용, 수행 절차를 작업 당시 함께 기록한다.