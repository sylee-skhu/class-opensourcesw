# Utterances의 장점

Utterances는 GitHub Issues를 사용하여 댓글 기능을 구현하는 시스템입니다. Disqus와 비교했을 때, 다음과 같은 여러 가지 장점을 가지고 있습니다.

## 1. 개인정보 보호

- **트래킹 없음**: Utterances는 사용자를 추적하지 않으며, 광고나 추적 스크립트가 없어 개인정보 보호에 좋습니다.
- **데이터 소유**: 댓글 데이터가 GitHub 저장소에 저장되어, 서비스 제공업체가 아닌 블로그 소유자가 데이터를 소유합니다.

## 2. GitHub 통합

- **GitHub 계정 사용**: 댓글을 남기는 사용자는 GitHub 계정을 사용하므로, 별도의 계정 생성 없이 기존의 GitHub 인프라를 사용할 수 있습니다.
- **이슈 관리**: 댓글이 GitHub Issues로 관리되어 개발자 친화적인 환경에서 댓글을 조율하고 관리할 수 있습니다.

## 3. 무료 사용

- **비용 없음**: Utterances는 완전히 무료로 사용할 수 있으며, 추가 비용 없이 모든 기능을 이용할 수 있습니다.

## 4. 쉬운 통합

- **간단한 설치**: 설정이 간단하고 GitHub 저장소에 몇 줄의 코드를 추가하는 것만으로도 댓글 기능을 쉽게 통합할 수 있습니다.
- **스타일 맞춤**: GitHub의 테마를 기반으로 하여 블로그 디자인과 일관성을 유지하며, GitHub의 light 혹은 dark 모드에 맞춰 자동으로 스타일이 변경됩니다.

## 5. 오픈소스

- **오픈소스**: Utterances는 오픈소스 프로젝트로, 커뮤니티의 기여를 받아 지속적으로 개선되고 있습니다.

## 6. 가볍고 빠름

- **경량**: 가벼운 JavaScript 로딩으로 페이지 로딩 시간에 거의 영향을 주지 않습니다.
- **빠른 로딩**: CDN을 통해 빠르게 로드되며 사용자 경험을 저하시키지 않습니다.

---

# Utterances를 이용한 댓글 기능 추가하기

Utterances는 GitHub Issues를 이용해 블로그 포스트에 댓글 기능을 추가할 수 있는 라이브러리입니다. 이 가이드는 GitHub Pages와 Jekyll에 Utterances를 적용하는 방법을 안내합니다.

## 전제 조건

- GitHub 계정이 있어야 합니다.
- 해당 블로그의 GitHub 저장소가 있어야 합니다.
- GitHub Pages로 호스팅 되는 Jekyll 블로그가 구축되어 있어야 합니다.

## 1. Utterances 스크립트 설정

1. **Utterances GitHub App 설치**: [Utterances GitHub App 페이지](https://github.com/apps/utterances)로 이동하여 GitHub 블로그 저장소에 대해 App을 설치합니다.

2. **댓글을 위한 GitHub Issue 작성 방식 결정**: 댓글을 각각의 포스트에 해당하는 Issue로 관리할지, 또는 다른 기준으로 관리할지 결정해야 합니다.

## 2. Utterances 스크립트 추가

1. **Utterances 설정**: [Utterances 웹사이트](https://utteranc.es/)에서 원하는 설정을 선택합니다. 설정을 완료하면, HTML `<script>` 태그를 생성해 줍니다.

2. **블로그 테마에 맞는 위치 선택**: 댓글을 표시하고자 하는 위치를 결정합니다. 대개 `_layouts/post.html` 파일 내에 적당한 위치를 찾습니다.

3. **스크립트 태그 삽입**: 위에서 생성된 `<script>` 태그를 복사하여, 블로그 테마 파일의 선택한 위치에 붙여넣습니다.

   예를 들어:

   ```html
   <script src="https://utteranc.es/client.js"
           repo="github-username/github-repo" // 여기서는 블로그의 GitHub 저장소를 입력
           issue-term="pathname" // 이 부분은 댓글이 달릴 Issue를 결정하는 방식을 설정
           theme="github-light" // 사용할 테마를 설정
           crossorigin="anonymous"
           async>
   </script>
   ```

## 3. 변경 사항 반영

1. 변경 사항을 Git을 통해 커밋하고 GitHub 저장소에 푸시합니다.

2. GitHub Pages가 자동으로 웹사이트를 재구성하도록 합니다.

## 4. 블로그에서 댓글 기능 확인

1. 블로그 포스트 페이지를 방문하여 Utterances 댓글 위젯이 정상적으로 작동하는지 확인합니다.

2. 처음 댓글이 게시되면, GitHub 저장소에 해당 내용이 Issue로 생성됩니다.

## 주의 사항

- GitHub Pages 사이트는 public이어야 하며, 저장소의 Issues가 활성화되어 있어야 합니다.
- 사용자가 댓글을 작성하려면 GitHub 계정이 있어야 합니다.