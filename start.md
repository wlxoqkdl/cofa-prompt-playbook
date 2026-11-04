# Cofa 시험 시작 가이드

응시 화면의 **최신 Cofa 공식 안내와 과제별 규정**을 먼저 확인한다. 공개 자료 복제와 참고 폴더 생성이 허용된 경우에만 이 플레이북을 가져온다. **시험 문제·코드·데이터·답안·결과물·로그·대화·상태 문서를 GitHub나 다른 외부 서비스로 보내거나 공유하지 않는다. 시험 중 `git push`는 금지한다.** 제출은 Cofa 공식 화면에서 진행한다.

## 1. Cofa 터미널에서 가져오기

Cofa 웹 IDE의 터미널에서 현재 위치를 확인한다. 파일 탐색기에서 **시험 프로젝트 루트의 `README.md`**를 열어 과제별 제한을 읽는다.

```sh
pwd
ls -a
```

시험 루트에 있고 참고 폴더를 둘 수 있는 위치와 제출 범위를 확인했다면 아래 명령을 실행한다. 과제에서 참고 폴더의 위치를 따로 정했다면 그 위치를 사용하고 이후 경로를 맞춘다.

```sh
git clone https://github.com/wlxoqkdl/cofa-prompt-playbook.git cofa-prompt-playbook
```

직접 실행하거나, 시험 루트에서 `codex`를 실행해 아래 지시를 Codex 입력창에 넣는다. 둘 중 하나만 하면 된다.

```text
과제 규정에서 공개 자료 반입과 참고 폴더 생성을 허용하는 것을 확인했어. 시험 프로젝트 루트인지 확인하고 cofa-prompt-playbook 경로가 없을 때만 아래 명령을 한 번 실행해 줘.
git clone https://github.com/wlxoqkdl/cofa-prompt-playbook.git cofa-prompt-playbook
기존 파일은 건드리지 마. 폴더가 이미 있거나 인증 요청·접근 오류가 나오면 멈추고 이유만 알려 줘. git push와 시험 자료 외부 전송은 금지야.
```

폴더가 이미 있으면 덮어쓰거나 지우지 말고 출처와 내용을 확인한다. 접근이 막히면 개인 계정·토큰을 쓰거나 우회하지 않는다. 필요하면 Cofa Helper에 확인하고, 플레이북 없이 진행할 때는 시험 루트 README를 기준으로 삼는다.

## 2. 복제 직후 Codex에 첫 지시 보내기

시험 루트에 머문 채 `codex`를 실행한다. 아래 텍스트는 **Codex 입력창**에 넣는다. 루트의 `README.md`는 시험 원본이고, `cofa-prompt-playbook/README.md`는 참고 문서다.

```text
시험 프로젝트 루트인지 확인해 줘. 시험 루트 README.md를 읽기 전용으로 읽어 과제별 제한을 확인한 뒤, cofa-prompt-playbook/RULES.md와 cofa-prompt-playbook/README.md를 읽어 줘. 최신 Cofa 공식 안내와 과제 규정을 우선 적용해.
시험 루트 README.md와 보호 대상은 수정·삭제·이동·이름 변경·덮어쓰기하지 마. 기존 코드와 설정은 내가 승인한 범위에서만 변경해. 시험 자료를 외부로 보내거나 git push를 실행하지 마.
지금은 파일 변경·설치·네트워크 요청 없이 적용할 핵심 규칙만 알려 주고 멈춰 줘.
```

## 3. 한 단계씩 진행하기

아래 지시를 복사해 `<단계 파일명>`만 바꾼다. 단계별 Markdown 전체를 붙여넣을 필요는 없다.

```text
cofa-prompt-playbook/RULES.md와 cofa-prompt-playbook/prompts/<단계 파일명>을 읽고 해당 단계만 진행해 줘. 시험 루트 README.md는 읽기 전용이야. 파일 쓰기나 변경이 필요하면 경로·이유·검증 방법을 먼저 알려 주고 승인 범위 안에서만 진행해 줘.
```

| 순서 | 할 일 |
| --- | --- |
| 1 | [01_discovery.md](prompts/01_discovery.md)로 필수 요구사항, 제출 조건, 기존 구조를 읽기 전용으로 확인한다. |
| 2 | 제공되는 경우 **Cofa 내부 메신저의 직원 AI(업무 담당자)**에게 사용자 불편, 업무 흐름, 예외와 성공 기준을 묻는다. 답변 요약은 Cofa 안에서만 다음 단계에 전달한다. |
| 3 | [02_planning.md](prompts/02_planning.md)로 인터뷰와 과제 요구사항을 종합해 우선순위와 검증 기준을 정한다. 계획 단계에서는 코드를 수정하지 않는다. |
| 4 | [03_project_status.md](prompts/03_project_status.md)로 승인한 계획을 기록한다. 과제가 허용하고 경로를 승인한 경우에만 시험 환경 안에 `PROJECT_STATUS.md`를 만든다. |
| 5 | [04_implementation.md](prompts/04_implementation.md)로 승인한 작업을 하나씩 구현하고 확인한다. |
| 6 | 막히면 [05_debugging.md](prompts/05_debugging.md)로 재현과 원인을 확인한 뒤 승인 범위에서 수정한다. [06_validation.md](prompts/06_validation.md)로 별도 세션에서 독립 검증한다. |
| 7 | 세션 전환이나 제출 전에는 [07_handoff.md](prompts/07_handoff.md)로 완료 근거와 남은 일을 정리한다. |

직원 AI에 보낼 첫 질문 예시

```text
이 업무에서 사용자가 가장 자주 겪는 불편은 무엇인가요? 현재 어떤 순서로 처리하고, 놓치면 안 되는 예외는 무엇인가요? 개선이 잘됐는지 확인할 기준도 알려 주세요.
```

## 4. 터미널 3개로 역할 나누기

Cofa 터미널의 `+`로 탭을 연다. 여러 탭을 쓰기 어렵다면 같은 역할을 차례로 수행한다.

| 터미널 | 역할 |
| --- | --- |
| 1 | 시험 루트에서 `codex`를 실행한다. 탐색·계획·구현과 승인된 상태 갱신을 맡는다. |
| 2 | 일반 터미널에서 과제에 맞는 서버·로컬 테스트 명령을 실행하고 로그를 확인한다. 서버가 실행 중인 탭은 열어 둔다. |
| 3 | 시험 루트에서 별도 `codex`를 실행해 독립 검증한다. 검증 중에는 1번의 편집을 잠시 멈추고, 수정은 검증 후 1번에서 진행한다. |

3번 Codex에 붙여넣기

```text
cofa-prompt-playbook/RULES.md와 cofa-prompt-playbook/prompts/06_validation.md를 읽어 줘. 시험 루트 README.md의 요구사항을 실제 코드와 검증 결과에 대조해 줘. 파일은 변경하지 말고 누락·결함·미검증 항목을 근거와 함께 보고해 줘. 파일을 쓰는 테스트나 빌드가 필요하면 먼저 알려 줘.
```

## 5. `/new` 전후로 작업 인계하기

기존 Codex 세션에 먼저 붙여넣는다.

```text
cofa-prompt-playbook/RULES.md와 cofa-prompt-playbook/prompts/07_handoff.md를 읽어 줘. 실제 변경, 테스트 결과, 남은 문제와 다음 작업 하나를 정리해 줘. 상태 문서 갱신이 승인된 경우에만 승인된 PROJECT_STATUS.md를 갱신해 줘. 다른 파일은 변경하지 마.
```

같은 시험 루트의 Codex 입력창에서 `/new`를 실행한다. 새 세션에 다음 지시를 붙여넣는다.

```text
시험 루트 README.md와 cofa-prompt-playbook/RULES.md를 다시 읽어 줘. 승인된 PROJECT_STATUS.md가 있으면 함께 읽고 실제 파일과 대조해 줘. 완료 근거, 남은 작업, 다음에 할 일 하나를 보고하고 멈춰 줘. 이미 완료된 작업을 다시 구현하지 마. 파일 변경·설치·외부 전송은 하지 마.
```

제출 전에 시험 루트 README와 보호 파일의 변경 여부를 확인한다. Git 프로젝트라면 시험 루트에서 아래 명령을 사용한다. 예상 밖 변경이 있으면 임의로 되돌리기 전에 확인한다.

```sh
git status --short
git diff HEAD -- README.md
```

공식 제출 대상과 저장 상태를 확인하고 참고 폴더가 제출 범위에 섞이지 않았는지 점검한다. 후속 서술형은 AI와 복사·붙여넣기 없이 직접 작성한다.
