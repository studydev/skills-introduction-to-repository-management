# Step 2: 협업 준비하기

여러분의 간단한 학교 웹사이트가 꽤 인기를 끌고 있습니다! 지난 교직원 회의에서 보여준 후, 미술 동아리의 Rodriguez 선생님과 체스 동아리의 Chen 선생님이 매우 흥분하며 다가왔습니다. 새로운 기능에 대한 아이디어가 넘쳐납니다!

- Rodriguez 선생님은 사진 갤러리를 추가하고 싶어합니다
- Chen 선생님은 체스/스포츠 활동을 위한 토너먼트 대진표 시스템을 꿈꿉니다! 🎨♟️

그들의 열정에 기쁘지만, 코드를 변경하기 시작하기 전에 가이드라인을 설정해야 한다는 것을 깨닫습니다. 봄 방학 직전에 충돌하는 변경사항이 등록 시스템을 망가뜨리는 것은 최악이니까요!

Mergington 고등학교의 다른 교사들에게 프로젝트를 개방한다는 것은 서로의 코드를 망가뜨리지 않고 어떻게 함께 협업할지 생각해야 한다는 뜻입니다.

**협업자(Collaborators)**는 저장소 설정을 통해 쓰기 권한을 부여한 사람들입니다.

- 저장소 설정을 보호하면서 다른 사람들에게 프로젝트 파일을 변경할 수 있는 권한을 제공합니다.
- 개인 저장소는 단순한 권한을 가집니다. 조직 저장소는 읽기, 쓰기, 유지관리, 관리자와 같은 유연한 권한을 허용합니다.

협업을 돕기 위해 GitHub는 두 가지 특별한 파일을 제공합니다:

1. **`CONTRIBUTING.md` 파일** - "기여 방법" 가이드입니다. 예시 내용:

   - 방과후 활동 웹사이트의 개발 환경을 준비하는 방법
   - 변경사항을 제안하는 과정
   - 일관성을 유지하기 위한 프로젝트의 코딩 스타일 선호도
   - 막혔을 때 도움을 요청하는 방법

1. **`CODEOWNERS` 파일** - 프로젝트의 특정 부분에 대한 책임자를 지정합니다.

   - 누군가 풀 리퀘스트를 생성하면 GitHub가 자동으로 적절한 사람에게 리뷰를 요청합니다.

## ⌨️ 활동: 환영하는 기여 가이드 만들기

내일 IT 동아리 회의가 있고, Rodriguez 선생님과 Chen 선생님이 프로젝트에 참여할 수 있도록 준비해야 합니다. 그들이 효과적으로 기여할 수 있도록 문서를 시작합시다.

1. 상단 탐색에서 **Code** 탭으로 돌아갑니다. `prepare-to-collaborate` 브랜치에 있는지 확인합니다.

   <img width="350" alt="올바른 브랜치를 보여주는 이미지" src="https://github.com/user-attachments/assets/68cd1e7a-1b34-47eb-9f0b-095d47442b12" />

1. 최상위 디렉토리에서 `CONTRIBUTING.md`라는 새 파일을 만듭니다 (대소문자 구분).

1. 환영 메시지를 추가합니다.

   ```md
   # Contributing to the Mergington High Extra-Curricular Activities Website

   Thank you for your interest in helping improve our school's website!
   Whether you want to add your club's activities, fix a bug, or suggest
   new features, this guide will help you get started. 🎉
   ```

1. 교사들이 빠르게 개발을 시작할 수 있는 안내를 추가합니다.

   ```md
   ## Development Setup

   1. Clone the repository to your computer.
   2. Install Python requirements: `pip install -r requirements.txt`.
   3. Run the development server: `python src/app.py`.
   4. Visit http://localhost:8000 in your browser to see the website.

   ## Making Changes

   1. Create a new branch for your changes.
      - Use descriptive names like `art-gallery-feature` or `fix-chess-signup`
   2. Make your changes and test them locally with sample student data.
      - Use the MongoDB extension to preview the included sample date.
   3. Push your branch and create a pull request.
   4. Wait for review and address any feedback.

   ## Code Style

   - Follow PEP 8 for Python code (backend).
   - Use clear, descriptive variable names (student_name, start_time, etc.)
   - Add comments to describe blocks of logic.
   ```

1. 도움을 받을 수 있는 섹션을 추가합니다.

   ```md
   ## Need help or have ideas?

   - Check the open issues first.
     - If your problem is there, add a comment or up-vote.
     - If not there, create a new issue. Be as descriptive as possible.
   - Ask in our weekly IT Club office hours (Thursdays at lunch in Room 203).
   - For other general problems, email the tech team at techclub@mergingtonhigh.example.edu
   ```

1. 오른쪽 상단에서 **Commit changes...** 버튼을 사용하고 `prepare-to-collaborate` 브랜치에 직접 커밋합니다.

## ⌨️ 활동: 코드 소유권 할당하기

다른 사람들이 참여하면서, 아키텍처와 핵심 기능에 영향을 미치는 변경사항에는 계속 관여하고 싶을 것입니다. 관련 파일에 여러분을 할당합시다.

1. 상단 탐색에서 **Code** 탭으로 돌아갑니다. `prepare-to-collaborate` 브랜치에 있는지 확인합니다.

1. 최상위 디렉토리에서 `CODEOWNERS`라는 새 파일을 만듭니다 (대소문자 구분, 확장자 없음).

1. 다음 내용을 추가합니다:

   ```codeowners
   # Core functionality - changes here should be rare!
   /src/app.py                   @{{ login }}
   /src/backend/database.py      @{{ login }}
   /src/backend/routers/auth.py  @{{ login }}

   # The frontend will need refactored soon to be more object oriented.
   /src/static/   @{{ login }}
   ```

1. 오른쪽 상단에서 **Commit changes...** 버튼을 사용하고 `prepare-to-collaborate` 브랜치에 직접 커밋합니다.

1. 파일이 커밋되면, Mona가 작업을 확인하고 피드백을 제공하며 다음 레슨을 공유할 때까지 잠시 기다립니다.

## ⌨️ 활동: (선택) 첫 번째 협업자 추가하기

동료가 사진 갤러리 기능 작업을 시작할 준비가 되었나요? 해봅시다!

> [!IMPORTANT]
> 이 단계는 GitHub 계정을 가진 다른 사람의 참여가 필요하므로 선택사항입니다.

1. 상단 탐색에서 **Settings** 탭을 선택합니다.

1. 왼쪽 탐색에서 **Collaborators**를 선택합니다.

1. **Manage access** 영역을 찾고 **Add people** 버튼을 클릭합니다.

   <img width="350" alt="" src="https://github.com/user-attachments/assets/686c32c6-11c2-4e69-bad1-39062d5b4376" />

1. 친구/동료의 GitHub 사용자명 또는 이메일을 입력한 다음 **Add to repository** 버튼을 누릅니다.

   <img width="350" alt="" src="https://github.com/user-attachments/assets/d0eaf344-baf0-4a9c-9291-c11e7a9fdaa3" />

> [!IMPORTANT]
> 개인 저장소에는 하나의 협업 역할 유형만 있습니다. "협업자"는 **쓰기** 권한을 받지만 **관리자** 권한은 받지 않습니다. 더 세밀한 권한이 필요하면 무료 [조직(organization)](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations)을 시작하고 [저장소 역할](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization)을 할당하는 것을 고려하세요.
