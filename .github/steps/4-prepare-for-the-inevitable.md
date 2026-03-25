# Step 4: 불가피한 것에 대비하기

교무실에서 커피를 마시며 앉아있다가 무언가를 깨닫습니다: 점점 더 많은 교사가 코드에 기여하면서, 보안 취약점이 발생하는 것은 시간 문제입니다. 😱

아무리 잘 관리된 코드베이스라도 결국에는 보안 문제에 직면하게 됩니다. GitHub가 제공하는 몇 가지 도구를 설정하여 그 날을 사전에 대비합시다:

1. **Dependabot** - 프로젝트에서 사용하는 상위 의존성에서 발견된 취약점을 추적하고 알림을 생성합니다. 안전한 버전으로 의존성을 업그레이드하는 풀 리퀘스트를 자동으로 생성합니다.

1. **코드 스캐닝(Code Scanning)** - 저장소의 코드를 분석하여 보안 취약점과 코딩 오류를 찾습니다. GitHub Copilot Autofix를 사용하여 이러한 알림에 대한 수정사항을 자동으로 제안합니다.

1. **보안 정책 및 비공개 취약점 보고(Security Policy and Private vulnerability reporting)** - 보안 연구자와 최종 사용자가 저장소 관리자에게 직접 취약점을 책임감 있게 보고할 수 있는 가이드와 간단한 양식을 제공합니다. 이를 통해 민감한 문제가 수정되기 전에 공개적으로 노출되는 것을 방지합니다.

> [!NOTE]
> 이것은 빠른 설정 가이드일 뿐입니다. 각 서비스에 대한 더 자세한 설정은 관련 GitHub Skills 실습 및/또는 GitHub 문서를 참조하세요.

## ⌨️ 활동: Dependabot으로 보안 업데이트 자동화하기

Dependabot을 기본 설정으로 구성하고, 열린 알림에 대한 수정사항을 자동으로 결합하여 풀 리퀘스트를 생성하도록 합시다. 이를 통해 최소한의 노력으로 최신 상태를 유지할 수 있습니다! 멋지네요!

> [!TIP]
> 더 깊이 알아보려면 [Secure Repository Supply Chain](https://github.com/skills/secure-repository-supply-chain) Skills 실습을 확인하세요!

1. 상단 탐색에서 **Settings** 탭을 선택합니다.

1. 왼쪽 탐색에서 **Advanced Security**를 선택합니다.

1. **Dependabot** 섹션을 찾습니다. 다음 설정과 일치하도록 확인하거나 변경합니다:

   - **Dependabot alerts**: `enabled`
   - **Dependabot security updates**: `enabled`
   - **Grouped security updates**: `enabled`

1. **Dependabot version updates**를 찾고 **Enable** 버튼을 클릭합니다. 설정 파일을 생성하는 편집기가 열립니다.

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/a4d7ae19-0439-4b78-bcbf-9fce5c5410ff" />

1. 왼쪽 파일 목록 상단에서 **Expand file tree** 버튼을 클릭하여 파일 목록을 표시합니다. 상단에서 브랜치를 `prepare-to-collaborate`로 변경합니다. 규칙 세트가 `main`에서 직접 파일을 변경하지 못하게 하는 것을 기억하세요.

   <img width="500" alt="image" src="https://github.com/user-attachments/assets/18a3cd1a-75ab-4e5e-a4c4-efd175d91ced" />

1. `package-ecosystem`을 `pip`으로 설정하여 Dependabot이 Python 요구사항을 자동으로 모니터링하도록 합니다.

   <img width="500" alt="image" src="https://github.com/user-attachments/assets/0bc90e67-4b71-4780-8272-20dc0fff5c4c" />

1. 오른쪽 상단에서 **Commit changes...** 버튼을 사용하고 `prepare-to-collaborate` 브랜치에 직접 커밋합니다.

## ⌨️ 활동: 코드 스캐닝으로 위험한 패턴 감지하기

고등학교의 우리 중 누구도 전문 소프트웨어 개발자가 아닙니다. 잠재적으로 안전하지 않은 작업을 하고 있을 때 알려줄 수 있도록 코드 스캐닝을 활성화합시다. 그리고, GitHub Copilot이 솔루션이 포함된 풀 리퀘스트를 생성하도록 설정합시다.

> [!TIP]
> 코드 스캐닝과 사용자 정의 쿼리 작성에 대해 더 알고 싶다면 이 실습을 마친 후 [Introduction to CodeQL](https://github.com/skills/introduction-to-codeql) Skills 실습을 확인하세요!

1. 상단 탐색에서 **Settings** 탭을 선택합니다.

1. 왼쪽 탐색에서 **Advanced Security**를 선택합니다.

1. **Code scanning** 섹션을 찾습니다. **Set up** 버튼을 클릭하고 **Default** 옵션을 선택하여 설정 패널을 엽니다.

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/5b3a89e5-c71a-44d9-b917-d1a21dc52181" />

1. **Enable CodeQL** 버튼을 클릭하여 기본 설정을 수락합니다.

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/6d5f7164-d8ed-4b5d-bbcf-8aed9e7acc5d" />

1. **Tools** 섹션 아래에서 **Copilot Autofix**가 `On`으로 설정되어 있는지 확인합니다.

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/b9d57e7a-f392-4c51-b137-f205a77adb79" />

## ⌨️ 활동: 보안 발견사항을 위한 안전한 경로 제공하기

자동화된 옵션이 준비되었으니, 실제 사람들이 발견한 보안 취약점을 안전한 방법으로 보고할 수 있는 가이드를 만들어 봅시다.

1. 상단 탐색에서 **Settings** 탭을 선택합니다.

1. 왼쪽 탐색에서 **Advanced Security**를 선택합니다.

1. **Private vulnerability reporting** 설정을 찾고 `enabled`인지 확인합니다.

1. 상단 탐색에서 **Security** 탭을 클릭합니다.

1. 왼쪽 탐색에서 **Policy** 옵션을 클릭합니다.

1. **Start setup** 버튼을 클릭합니다. `SECURITY.md` 파일을 생성하는 편집기가 시작됩니다.

   <img width="350" alt="" src="https://github.com/user-attachments/assets/183b9fcc-1521-47fd-8165-b476a8ccb370"/><br/>

   <img width="350" alt="" src="https://github.com/user-attachments/assets/36c272d1-bc4a-48c8-b234-56173a214cdb"/>

1. 왼쪽 파일 목록 상단에서 **Expand file tree** 버튼을 클릭하여 파일 목록을 표시합니다. 상단에서 브랜치를 `prepare-to-collaborate`로 변경합니다. 규칙 세트가 `main`에서 직접 파일을 변경하지 못하게 하는 것을 기억하세요.

1. 제공된 템플릿은 무시하고 Mergington 고등학교 IT 부서의 권장사항을 사용합니다. 다음 내용을 추가합니다:

   > 💡**팁** 같은 파일이 포함되지 않은 브랜치로 전환하면 편집기가 비어집니다. **Restore** 버튼을 눌러 이전 편집기의 내용을 복구하세요.

   ```markdown
   # Mergington High School Security Policy

   ## Reporting a Vulnerability

   At Mergington High, we take the security of our Extra-Curricular Activities website seriously, especially
   since it contains student information. If you discover a security vulnerability, please follow these steps:

   1. **Do not** create an issue on this repository, disclose the vulnerability publicly, or discuss it with other teachers/students.
   1. In the top navigation of this repository, click the **Security** tab.
   1. In the top right, click the **Report a vulnerability** button.
   1. Fill out the provided form. It will request information like:
      - A description of the vulnerability
      - Steps to reproduce the issue
      - Potential impact on student data or website functionality
      - Suggested fix (if you have one)
   1. Email the IT Club faculty advisor at techsupport@mergingtonhigh.example.edu and inform them you have made a report. **Do not** include any vulnerability details.

   ## Response Timeline

   - We will acknowledge receipt of your report within 2 school days
   - We will provide an initial assessment within 5 school days
   - Critical issues affecting student data will be addressed immediately
   - We will create a private fork to solve the issue and invite you as a collaborator so you can see our progress and contribute.

   ## Thank You

   Your help in keeping our school's digital resources secure is greatly appreciated!
   Responsible disclosure of security vulnerabilities helps protect our entire school community.
   ```

1. 오른쪽 상단에서 **Commit changes...** 버튼을 사용하고 `prepare-to-collaborate` 브랜치에 직접 커밋합니다.

1. 파일이 커밋되면, Mona가 작업을 확인하고 피드백을 제공하며 다음 레슨을 공유할 때까지 잠시 기다립니다.
