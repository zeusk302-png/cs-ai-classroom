# Google 검색 등록

사이트의 SEO 설정과 사이트맵은 자동 배포에 포함됩니다. Google의 실제 색인 여부는 Search Console에서 확인합니다.

1. [Google Search Console](https://search.google.com/search-console/)에 로그인하고 **URL 접두어** 속성을 추가합니다.
2. 주소에 `https://zeusk302-png.github.io/cs-ai-classroom/`를 입력하고 **HTML 태그** 인증 방법을 선택합니다. 받은 `google-site-verification` 태그를 프로젝트 관리자에게 전달해 사이트에 반영한 뒤 인증합니다. GitHub Pages 제공 도메인이므로 이 프로젝트에서는 DNS 인증보다 URL 접두어 방식이 적합합니다.
3. 인증 후 **Sitemaps**에서 `sitemap.xml`을 제출합니다. 전체 주소는 `https://zeusk302-png.github.io/cs-ai-classroom/sitemap.xml`입니다. **URL 검사**에서 홈과 대표 강의의 공개 URL을 검사하고 색인 생성 요청을 합니다.

인증 태그는 `planning/search-console-config.json`의 `google_site_verification` 값으로 저장하면 이후 배포에도 유지됩니다. 태그 전체 대신 `content` 속성의 값만 저장합니다. 인증 토큰을 파일에 넣는 것과 Search Console의 인증 버튼을 눌러 소유권을 확인하는 것은 별도 단계입니다.

```json
{"google_site_verification": "Google에서 받은 content 값"}
```

`/cs-ai-classroom/robots.txt`는 안내용으로 제공하지만 Google이 사용하는 robots.txt는 호스트 루트인 `https://zeusk302-png.github.io/robots.txt`입니다. 이 프로젝트의 하위 경로 robots.txt만으로 크롤링 정책이나 사이트맵 발견을 보장할 수 없습니다. Search Console에서 사이트맵을 직접 제출하세요.

사이트맵은 배포된 과목 안내와 본문 페이지의 대표 URL을 포함합니다. 운영·집필 현황 페이지 및 아직 전체 본문이 없는 번역 샘플은 `noindex,follow`로 제외합니다. 사이트맵은 갱신 때 함께 재생성되며, 근거 없는 `lastmod` 날짜를 기재하지 않습니다.

SEO 설정은 검색엔진의 이해와 발견을 돕습니다. 실제 색인 시점과 검색 순위는 Google이 결정하므로 노출 여부를 Search Console에서 확인해야 합니다.
