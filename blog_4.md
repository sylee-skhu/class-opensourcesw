# Google Analytics를 Jekyll 블로그에 적용하기

Google Analytics는 웹사이트의 트래픽을 분석하고 사용자의 행동을 이해하는 데 도움을 주는 서비스입니다. 이를 Jekyll 블로그에 적용하면 방문자의 활동을 추적하고 분석할 수 있습니다.

## 설정 단계

### 1. Google Analytics 계정 설정

1. [Google Analytics 웹사이트](https://analytics.google.com)로 이동하여 로그인하거나 계정을 생성합니다.
2. **관리** 탭으로 이동하여 새로운 **계정**을 생성합니다.
3. 새 웹사이트에 대한 **속성**을 설정합니다.
4. 추적 ID를 받습니다.

### 2. Jekyll 블로그에 추적 코드 추가

1. Jekyll 사이트의 `_config.yml` 파일을 엽니다.
2. analytics 관련 설정이 있는지 찾아보고, 적절히 수정합니다.
3. Google Analytics 추적 코드를 포함할 설정이 없는 경우, 직접 HTML 파일을 설정합니다. 보통은 `_includes` 폴더 내의 `head.html` 파일을 사용합니다.
4. `head.html` 파일을 열고, 다음 추적 코드 스니펫을 `</head>` 태그 바로 앞에 붙여넣습니다.

   ```html
   {% if site.google_analytics %}
   <script async src="https://www.googletagmanager.com/gtag/js?id={{ site.google_analytics }}"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());

     gtag('config', '{{ site.google_analytics }}');
   </script>
   {% endif %}
   ```

5. 모든 변경사항을 저장하고 GitHub에 커밋 및 푸시합니다.

## Google Analytics 사용하기

설정 후 Google Analytics는 자동으로 데이터를 수집하기 시작합니다. 수집된 데이터를 보려면 다음 단계를 따르세요:

1. [Google Analytics 대시보드](https://analytics.google.com)로 이동합니다.
2. 좌측 메뉴에서 **실시간**을 클릭하여 실시간 방문자 수를 확인하는 등 다양한 섹션에서 방문자의 여러 측면을 분석합니다.
3. 대시보드를 사용자 정의하여 가장 중요한 지표를 한눈에 볼 수 있도록 설정할 수 있습니다.
