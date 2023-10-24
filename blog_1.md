# GitHub Pages와 Jekyll로 블로그 시작하기

## 1. 준비 사항

- GitHub 계정
- [Visual Studio Code](https://code.visualstudio.com/) 설치
- Git 설치 (Windows의 경우 [Git for Windows](https://gitforwindows.org/), Mac의 경우 터미널에서 `brew install git` 실행)

## 2. GitHub 저장소 생성

1. GitHub에 로그인한 후, 새로운 저장소를 생성합니다. 저장소 이름은 `[사용자명].github.io`로 지정합니다.

## 3. Jekyll 설치 및 초기 설정 (Windows & Mac)

1. **Ruby 설치**
   - Windows: [RubyInstaller](https://rubyinstaller.org/) 사용 (Jekyll은 32비트이므로 x86 버전 선택)
   - Mac: `brew install ruby`

2. **Jekyll 및 bundler 설치**
   - Windows: 시작 > Start Command Prompt with Ruby 실행
```bash
gem install jekyll bundler
```

3. **새로운 Jekyll 사이트 생성**
```bash
jekyll new [사용자명].github.io
```

4. 생성된 디렉토리로 이동
```bash
cd [사용자명].github.io
```

## 4. Visual Studio Code로 프로젝트 열기

1. Visual Studio Code를 엽니다.
2. **File** > **Open** (또는 **Open Folder** on Windows)를 선택하고, 위에서 생성한 Jekyll 사이트 디렉토리를 선택합니다.

## 5. Git 연동 및 GitHub에 Push

1. 터미널에서 다음 명령어를 실행하여 Git 초기화:
```bash
git init
```

2. GitHub 저장소를 remote로 추가:
```bash
git remote add origin https://github.com/[사용자명]/[사용자명].github.io.git
```

3. 파일들을 커밋하고 GitHub에 Push:
```bash
git add .
git commit -m "Initial commit"
git push -u origin main
```

## 6. 블로그 확인

브라우저에서 `https://[사용자명].github.io`로 접속하여 블로그가 정상적으로 동작하는지 확인합니다.