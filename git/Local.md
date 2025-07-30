## Git 설치 (Windows)

- **Git for Windows** 설치 파일 다운로드:
    - [https://git-scm.com/](https://git-scm.com/) 접속
    - 최신 버전의 설치 파일 다운로드
- 설치 시 주의사항:
    - 기본 설정 그대로 진행해도 무방
    - "Git Bash Here" 우클릭 메뉴 확인
#gitbash
## Git Bash 실행

- **시작 메뉴** 또는 바탕화면에서 **Git Bash** 실행
- 커맨드 라인 인터페이스 제공 (Linux 스타일 셸 환경)
#linux
## 설치 확인

```bash
git --version
```

- Git이 정상적으로 설치되었는지 확인
- 예시: `git version 2.45.0.windows.1`

## Git 로컬 저장소 설정

### 저장소 초기화

```bash
git init
```

- 현재 디렉토리를 Git 저장소로 초기화
- `.git` 폴더 생성됨

### `.git` 디렉토리 삭제

```bash
rm -rf .git
```

- `.git`은 Git 저장소의 설정과 이력을 담는 숨김 폴더
- 실수로 잘못된 초기화 시 삭제 후 재초기화할 때 사용
- **주의: 삭제 시 기존 커밋 이력 사라짐**

### 상태 확인

```bash
git status
```

- 변경된 파일, staged 상태 등 확인
- 초기 상태: "No commits yet"

### 파일 스테이징

```bash
git add 파일명
```

- 특정 파일을 staged 상태로 만듦
#stage

```bash
git add .
```

- 모든 변경 파일을 stage

### 스테이징 해제

```bash
git reset 파일명
```

- 특정 파일을 staged 상태에서 해제

```bash
git reset
```

- 전체 스테이지 상태 해제

## 커밋 관련 설정 및 문제 해결

### 사용자 정보 설정

```bash
git config --global user.name "홍길동"
git config --global user.email "hong@example.com"
```

- 최초 커밋 전 필수 설정
#config #github 
### 커밋 생성

```bash
git commit -m "커밋 메시지"
```

- 메시지를 직접 명시하여 커밋

### 편집기 문제 (vi 편집기)

```bash
git commit
```

- 메시지 없이 커밋 시 vi 편집기 열림
- 종료 방법:
    - 입력 모드 진입: `i`
    - 메시지 작성
    - 명령 모드로 전환: `Esc`
    - 저장 후 종료: `:wq`
    - 취소: `:q!`
#vi편집기

### ​커밋 메시지 수정

```bash
git commit --amend
```

- 가장 마지막 커밋 메시지 수정
- vi 편집기 사용됨

### 커밋 취소

```bash
git reset --soft HEAD~1
```

- 마지막 커밋만 취소 (파일은 staged 상태 유지)

```bash
git reset --mixed HEAD~1
```

- 마지막 커밋 취소 + staging 해제 (파일은 보존됨)

```bash
git reset --hard HEAD~1
```

- 마지막 커밋 취소 + staging 해제 + 파일 원상복구 (주의!)

## Git 로그 확인

```bash
git log
```

- 커밋 이력 전체 출력

```bash
git log --oneline
```

- 한 줄 요약으로 보기

```bash
git log --graph --oneline --all
```

- 브랜치 및 머지 기록을 시각적으로 보기

```bash
git log --stat
```

- 파일별 변경 통계 표시