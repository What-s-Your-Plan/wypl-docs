# Git Convention

해당 저장소에서 사용하는 깃 사용에 대한 약속입니다.

## 1. Git-Flow 전략

1. **main** : 제품으로 출시될 수 있는 브랜치
2. **dev** : 다음 출시 버전을 개발하는 브랜치
3. **feat** : 기능을 개발하는 브랜치
4. **release** : 이번 출시 버전을 준비하는 브랜치
5. **hotfix** : 출시 버전에서 발생한 버그를 수정 하는 브랜치

<img src="https://github.com/user-attachments/assets/a7ebc408-54d2-4c34-b455-dc442dc8b78b" alt="git-flow" height="600" />

### 1.1. Branch Naming

`feat`,`hotfix` 와 같은 타입의 뒤에 이슈 번호를 붙여서 생성합니다.

**예시**

- feat/#1
- hotfix/#3

## 2. Commit Message Convention

### 2.1. Commit Message Structure

- 기본적인 커밋 메시지 구조 (각 파트는 빈줄로 구분한다.)

  > 제목 (Type: Subject)
  >
  > (한줄 띄어 분리)
  >
  > 본문 (Body)
  >
  > (한줄 띄어 분리)
  >
  > 꼬리말 (Footer)

### 2.2. Commit Type

- 커밋의 타입 구성

  > 태그: 제목
  >
  > 제목 으로 :뒤에만 space를 넣는다.

  | Tag Name         | Description                                                  |
  | ---------------- | ------------------------------------------------------------ |
  | Feat             | 새로운 기능을 추가                                           |
  | Fix              | 버그 수정                                                    |
  | Design           | CSS 등 사용자 UI 디자인 변경                                 |
  | !BREAKING CHANGE | 커다란 API 변경의 경우                                       |
  | !HOTFIX          | 급하게 치명적인 버그를 고쳐야하는 경우                       |
  | Style            | 코드 포맷 변경, 세미 콜론 누락, 코드 수정이 없는 경우        |
  | Refactor         | 프로덕션 코드 리팩토링                                       |
  | Comment          | 필요한 주석 추가 및 변경                                     |
  | Docs             | 문서 수정                                                    |
  | Test             | 테스트 코드, 리펙토링 테스트 코드 추가, Production Code(실제로 사용하는 코드) 변경 없음 |
  | Chore            | 빌드 업무 수정, 패키지 매니저 수정, 패키지 관리자 구성 등 업데이트, Production Code 변경 없음 |
  | Rename           | 파일 혹은 폴더명을 수정하거나 옮기는 작업만인 경우           |
  | Remove           | 파일을 삭제하는 작업만 수행한 경우                           |

  추가적인 문맥 정보를 제공하기 위한 목적으로 괄호 안에 적을 수도 있다.

​ **해당 프로젝트에서는 괄호안에 깃허브의 이슈 번호를 작성합니다.**

```
ex)
 Feat(#1)
 Fix(#3)
```

### 2.3. Subject

- 제목은 50글자 이내로 작성한다.

- 첫글자는 대문자로 작성한다.

- 마침표 및 특수기호는 사용하지 않는다.

- 영문으로 작성하는 경우 동사(원형)을 가장 앞에 명령어로 작성한다.

- 과거시제는 사용하지 않는다.

- 간결하고 요점적으로 즉, 개조식 구문으로 작성한다.

  ```
  ex)
  Fixed --> Fix
  Added --> Add
  Modified --> Modify
  ```

### 2.4. Body

- 72이내로 작성한다.
- 최대한 상세히 작성한다. (코드 변경의 이유를 명확히 작성할수록 좋다)
- 어떻게 변경했는지보다 무엇을, 왜 변경했는지 작성한다.

### 2.5. Footer

- 선택사항

- issue tracker ID 명시하고 싶은 경우에 작성한다.

- 유형: #이슈 번호 형식으로 작성한다.

- 여러 개의 이슈번호는 쉼표(,)로 구분한다.

- 이슈 트래커 유형은 다음 중 하나를 사용한다.

  Fixes: 이슈 수정중 (아직 해결되지 않은 경우)Resolves: 이슈를 해결했을 때 사용Ref: 참고할 이슈가 있을 때 사용Related to: 해당 커밋에 관련된 이슈번호 (아직 해결되지 않은 경우)

  ```
  ex)
  Fixes: #45 Related to: #34, #23
  ```

### 2.6. Example

**예시 1**

```
Feat: 회원 가입 기능 구현

SMS, 이메일 중복확인 API 개발

Resolves: #123
Ref: #456
Related to: #48, #45
```

**예시 2**

```
feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Typically a hyphen or asterisk is used for the bullet, preceded
by a single space, with blank lines in between, but conventions
vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
```

# Ref

1. [[Git] Commit Message Convention](https://velog.io/@archivvonjang/Git-Commit-Message-Convention)
