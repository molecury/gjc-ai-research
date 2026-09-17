# Git 및 GitHub 연결 가이드

현재 이 컴퓨터에서는 `git` 명령이 확인되지 않았으므로 먼저 Git을 설치해야 합니다.

## 1. Git 설치

Ubuntu/Debian 계열:

```bash
sudo apt update
sudo apt install git
git --version
```

설치에는 관리자 권한과 네트워크 연결이 필요합니다.

## 2. 작성자 정보 설정

GitHub에서 사용할 이름과 이메일로 바꿔 실행합니다.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
```

설정 확인:

```bash
git config --global --list
```

공개 커밋에서 실제 이메일을 숨기려면 GitHub의 `noreply` 이메일을 사용할 수 있습니다.

## 3. 로컬 저장소 만들기

```bash
cd /home/koco/research-log-template
git init
git add .
git commit -m "docs: initialize AI-assisted research log"
```

## 4. GitHub 원격 저장소 만들기

GitHub 웹사이트에서 새 저장소를 생성합니다. 로컬에 이미 파일이 있으므로 GitHub의 README, `.gitignore`, 라이선스 자동 생성 옵션은 선택하지 않는 편이 간단합니다.

민감한 연구라면 반드시 **Private repository**로 만드세요.

## 5. 원격 저장소 연결

### SSH 방식

GitHub에 SSH 키를 등록한 뒤 실행합니다.

```bash
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git push -u origin main
```

### HTTPS 방식

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

HTTPS 인증에는 계정 비밀번호가 아니라 Personal Access Token 또는 GitHub의 자격 증명 도구가 필요할 수 있습니다. 토큰을 파일이나 커밋에 저장하면 안 됩니다.

연결 확인:

```bash
git remote -v
git status
```

## 6. 일상적인 기록 흐름

```bash
git status
git diff
git add research/2026-09-17-topic-name
git commit -m "research: summarize topic-name deep research"
git push
```

`git add .`보다 검토한 파일이나 디렉터리를 명시적으로 추가하면 민감한 파일의 실수 커밋을 줄일 수 있습니다.

## 공개 전 확인

- API 키, 토큰, 로그인 정보가 없는가?
- 개인 정보와 환자·참여자 정보가 없는가?
- 공개 권한이 없는 데이터 또는 논문 전문이 없는가?
- AI가 만든 내용을 사람이 검증했는가?
- 출처와 접근일이 기록되어 있는가?
- 대용량 원본 데이터 대신 위치, 버전, 체크섬을 기록할 수 있는가?

