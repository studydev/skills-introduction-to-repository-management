# Step 1: 코드 보호하기

Mergington 고등학교에서 바쁜 한 달이었습니다! 방과후 활동을 관리하는 간단한 웹사이트가 정말 큰 인기를 끌고 있습니다. 몇 가지 활동에 대한 기본 가입 양식으로 시작한 것이 학교 활동의 절반을 차지하는 핵심 플랫폼으로 성장했습니다. 📚✨

Martinez 교장 선생님이 여러분의 작업에 매우 감동하여 지난 교직원 회의에서 모든 동아리가 웹사이트를 사용하기 시작해야 한다고 발표했습니다. 이것이 신나는 일이지만, 약간 긴장됩니다 - 가을 활동 박람회 직전에 실수로 변경하여 시스템이 고장나는 것은 최악이니까요! 😰

더 많은 교사들이 Mergington 고등학교 활동 웹사이트를 돕기 시작할 때, 보호 조치를 추가하는 것이 중요합니다. 다행히 GitHub는 저장소를 보호하는 여러 가지 방법을 제공합니다:

1. **저장소 규칙 세트(Repository Rulesets)** - 다음을 제한하는 보호 조치를 제공합니다:

   - 중요한 브랜치에 직접 코드 푸시하기
   - 브랜치 삭제 또는 이름 변경
   - 강제 푸시(기록을 덮어쓸 수 있음)
   - (그 외 많은 것들)

1. **`.gitignore`** - 이 특별한 파일은 Git이 추적하지 않아야 할 파일을 알려줍니다:

   - 코드가 실행 중에 생성하는 임시 파일
   - 민감한 정보가 포함된 비밀 설정 파일
   - 다른 개발자에게 필요하지 않은 시스템 파일

> [!TIP]
> 이 설정들을 학교 졸업앨범의 편집 과정처럼 생각하세요. 다양한 학생 위원회가 사진을 찍고 기사를 작성한 다음, 졸업앨범 편집장이 모든 것이 제대로 흘러가도록 조정합니다. 마지막으로, 교사/자문위원이 모든 콘텐츠가 적절한지 승인합니다.

## ⌨️ 활동: (선택) 방과후 활동 사이트 살펴보기

<details>
<summary>단계 보기</summary>

[GitHub Copilot 시작하기](https://github.com/skills-kr/getting-started-with-github-copilot/) 실습에서 방과후 활동 웹사이트를 개발했습니다. 다음 단계를 따라 개발 환경을 시작하고 시도해 볼 수 있습니다.

> ❗ **중요:** 개발 환경을 열고 애플리케이션을 실행하는 것은 이 실습을 완료하는 데 **필수가 아닙니다**. 원한다면 이 활동을 건너뛸 수 있습니다.

1. 아래 버튼을 우클릭하여 새 탭에서 **Create Codespace** 페이지를 엽니다. 기본 설정을 사용합니다.

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. 환경이 준비될 때까지 잠시 기다립니다. 모든 요구사항과 서비스가 자동으로 설치됩니다.

1. **GitHub Copilot**과 **Python** 확장이 설치되고 활성화되어 있는지 확인합니다.

   <img width="300" alt="VS Code용 copilot 확장" src="https://github.com/user-attachments/assets/ef1ef984-17fc-4b20-a9a6-65a866def468" /><br/>
   <img width="300" alt="VS Code용 python 확장" src="https://github.com/user-attachments/assets/3040c0f5-1658-47e2-a439-20504a384f77" />

1. 애플리케이션을 실행해 봅니다. 왼쪽 사이드바에서 **실행 및 디버그** 탭을 선택한 다음 **디버깅 시작** 아이콘을 누릅니다.

   <details>
   <summary>📸 스크린샷 보기</summary><br/>

   <img width="300" alt="실행 및 디버그" src="https://github.com/user-attachments/assets/50b27f2a-5eab-4827-9343-ab5bce62357e" />

   </details>

   <details>
   <summary>🤷 문제가 있나요?</summary><br/>

   **실행 및 디버그** 영역이 비어있다면 VS Code를 다시 로드해 보세요: 명령 팔레트(`Ctrl`+`Shift`+`P`)를 열고 `Developer: Reload Window`를 검색합니다.

   <img width="300" alt="빈 실행 및 디버그 패널" src="https://github.com/user-attachments/assets/0dbf1407-3a97-401a-a630-f462697082d6" />

   </details>

1. **포트** 탭을 사용하여 웹페이지 주소를 찾고, 열어서 실행 중인지 확인합니다.

   <details>
   <summary>📸 스크린샷 보기</summary><br/>

   <img width="350" alt="포트 탭" src="https://github.com/user-attachments/assets/8d24d6b5-202d-4109-8174-2f0d1e4d8d44" />

   ![Mergington 고등학교 WebApp 스크린샷](https://github.com/user-attachments/assets/5e1e7c1e-1b0e-4378-a5af-a266763e6544)

   </details>

</details>

## ⌨️ 활동: 브랜치 규칙 세트 추가하기

시작하기 위해, 아무도 실수로 동아리 등록 시스템을 망가뜨리지 않도록 보호 조치를 추가합시다.

1. 필요한 경우 다른 탭을 열고 이 저장소로 이동합니다. **Settings** 탭에서 시작합니다.

1. 왼쪽 탐색에서 **Rules** 영역을 확장하고 **Rulesets**를 선택합니다.

1. **New ruleset** 드롭다운을 클릭하고 **New branch ruleset**을 선택합니다.

   <img width="250" alt="image" src="https://github.com/user-attachments/assets/1e9fd519-1421-4d6b-b654-a3fe53a8fb75" />

1. **Ruleset Name**을 `Protect main`으로 설정하고 **Enforcement status**를 `Active`로 변경합니다.

   <img width="250" alt="image" src="https://github.com/user-attachments/assets/ce30fd34-39b5-4e22-b348-4af61fd05cd1" />

1. **Targets** 섹션을 찾고 **Add target** 드롭다운을 사용하여 2개의 항목을 추가합니다:

   1. **Include default branch** 옵션을 추가하여 기본 브랜치를 전환하여 보호를 우회하지 못하도록 합니다.

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/217263cc-d5c2-4ac0-b03c-a72494e5c812" />

   1. **include by pattern** 옵션을 사용하고 패턴 `main`을 입력합니다.

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/968c9ed8-b051-44eb-af42-d99670ad31fd" />

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/ddc52767-d93e-4c9e-a77a-90c3b5c08fb5" />

1. **Rules** 섹션을 찾고 다음 항목이 체크되어 있는지 확인합니다.

   - [x] Restrict deletions
   - [x] Require a pull request before merging
     - Required approvals: `0`
     - [x] Require review from Code Owners
   - [x] Block force pushes

1. 아래로 스크롤하여 **Create** 버튼을 클릭하여 규칙 세트를 저장합니다.

## ⌨️ 활동: `.gitignore` 파일 만들기

많은 교사들이 다른 도구를 사용하므로, 불필요한 파일을 실수로 커밋하지 않도록 합시다.

1. 상단 탐색에서 **Code** 탭으로 돌아가 `main` 브랜치에 있는지 확인합니다.

1. 파일 목록 위에서 **Add file** 드롭다운을 클릭하고 **Create new file**을 선택합니다.

   <img width="300" alt="새 파일 버튼" src="https://github.com/user-attachments/assets/8f3f8da8-1471-485a-9df5-8c03ecba2d8e"/>

1. 파일 이름으로 `.gitignore`를 입력합니다. 템플릿 선택기는 무시하고 직접 만들겠습니다. 아래 예시 내용을 복사하여 붙여넣습니다.

   <img width="350" alt="새 파일 미리보기" src="https://github.com/user-attachments/assets/580d1a63-a264-4d44-8901-50ad708b8822"/>

   ```gitignore
   # Python backend for club management
   __pycache__/
   *.py[cod]      # Python compiled files
   *$py.class
   *.so
   .Python
   env/
   .env           # Where database passwords are stored
   venv/          # Virtual environment for testing
   .venv

   # Teacher IDE settings
   .vscode/       # Ms. Rodriguez uses VS Code
   .idea/         # Mr. Chen uses PyCharm

   # Local development & testing
   instance/
   .pytest_cache/
   .coverage      # Test coverage reports
   htmlcov/

   # Staff computer files
   .DS_Store      # For teachers with Macs
   Thumbs.db      # For teachers with Windows
   ```

1. 오른쪽 상단에서 **Commit changes...** 버튼을 선택합니다. `main` 브랜치에 커밋할 수 없다는 것을 확인하세요! 규칙 세트가 작동하고 있습니다! 멋지네요!

   <img width="400" alt="image" src="https://github.com/user-attachments/assets/4e85948d-75c8-4c13-8ddd-4707bf9b0805" />

1. 브랜치 이름으로 `prepare-to-collaborate`를 입력한 다음 **Propose changes** 버튼을 클릭합니다. 새 풀 리퀘스트를 시작하는 새 페이지로 이동됩니다.

1. 제목을 `Prepare to collaborate`로 설정하고 **Create pull request** 버튼을 클릭합니다. 더 많은 협업 관련 변경사항을 추가할 예정이므로 **아직 병합하지 마세요**.

1. 파일이 커밋되면, Mona가 작업을 확인하고 피드백을 제공하며 다음 레슨을 공유할 때까지 잠시 기다립니다.

> [!TIP]
> GitHub와 커뮤니티가 다양한 상황에 맞는 [`.gitignore` 샘플 파일](https://github.com/github/gitignore) 저장소를 만들었습니다. 꼭 확인해 보세요!

<details>
<summary>🤷 문제가 있나요?</summary><br/>

`.gitignore` 파일을 `prepare-to-collaborate` 브랜치에 푸시했는지 확인하세요. 파일명과 브랜치명 모두 정확해야 합니다!

</details>
