# 지역홍보 페이지 - MkDocs 프로젝트

우리 지역의 아름다운 자연과 풍부한 문화유산을 소개하는 공식 홍보 웹사이트입니다.

## 🌟 프로젝트 개요

이 프로젝트는 MkDocs와 Material 테마를 사용하여 제작된 지역 관광 홍보 사이트입니다. 방문객들에게 우리 지역의 매력을 효과적으로 전달하고, 관광 정보를 체계적으로 제공합니다.

## 📋 주요 기능

- **반응형 디자인**: 모바일, 태블릿, 데스크톱 모든 기기에서 최적화
- **다국어 지원**: 한국어 기본, 추후 영어/중국어/일본어 확장 가능
- **검색 기능**: 사이트 내 통합 검색
- **다크/라이트 모드**: 사용자 선호에 따른 테마 전환
- **SEO 최적화**: 검색엔진 최적화 적용

## 🗂️ 사이트 구조

```
📁 지역홍보 사이트
├── 🏠 홈
├── 📖 지역 소개
│   ├── 개요
│   ├── 역사
│   └── 지리
├── 🏞️ 관광 명소
│   ├── 자연 명소
│   ├── 문화 유적
│   └── 체험 활동
├── 🍽️ 맛집 & 특산품
│   ├── 지역 맛집
│   └── 특산품
├── 🎉 축제 & 이벤트
│   ├── 연중 축제
│   └── 계절별 이벤트
├── 🚗 교통 & 숙박
│   ├── 교통 안내
│   └── 숙박 시설
├── 📞 연락처
└── 🛠️ 개발자 (기여 가이드)
```

## ⚙️ MkDocs 설정 가이드 (mkdocs.yml)

`mkdocs.yml` 파일은 MkDocs 사이트의 모든 설정을 관리하는 핵심 파일입니다. 각 섹션별 상세 설명은 다음과 같습니다.

### 📄 사이트 메타데이터
```yaml
site_name: 우리 지역 홍보 사이트          # 사이트 제목 (브라우저 탭, 헤더에 표시)
site_description: 아름다운 우리 지역을 소개하는 공식 홍보 페이지  # SEO용 설명
site_author: 지역 관광청                  # 사이트 작성자 정보
```

- **site_name**: 브라우저 탭과 사이트 헤더에 표시되는 제목
- **site_description**: 검색엔진 최적화를 위한 사이트 설명
- **site_author**: 메타데이터에 포함되는 작성자 정보

### 🔗 저장소 설정
```yaml
repo_name: local-promotion-site           # GitHub 저장소 이름
repo_url: https://github.com/your-username/local-promotion-site  # 저장소 URL
```

- **repo_name**: 사이트 우상단에 표시되는 저장소 이름
- **repo_url**: GitHub 저장소 링크 (편집 버튼 등에 사용)

### 🎨 테마 설정
```yaml
theme:
  name: material                          # Material 테마 사용
  language: ko                            # 한국어 설정
  palette:                                # 색상 팔레트 설정
    - scheme: default                     # 라이트 모드
      primary: green                      # 기본 색상
      accent: light green                 # 강조 색상
      toggle:                             # 모드 전환 버튼
        icon: material/brightness-7       # 라이트 모드 아이콘
        name: 다크 모드로 전환              # 툴팁 텍스트
    - scheme: slate                       # 다크 모드
      primary: green
      accent: light green
      toggle:
        icon: material/brightness-4       # 다크 모드 아이콘
        name: 라이트 모드로 전환
  features:                               # 테마 기능 활성화
    - navigation.tabs                     # 상단 탭 네비게이션
    - navigation.sections                 # 섹션별 네비게이션
    - navigation.expand                   # 네비게이션 자동 확장
    - navigation.top                      # 맨 위로 가기 버튼
    - search.highlight                    # 검색 결과 하이라이트
    - search.share                        # 검색 결과 공유
    - content.code.copy                   # 코드 복사 버튼
```

#### 주요 테마 기능 설명
- **navigation.tabs**: 주요 섹션을 상단 탭으로 표시
- **navigation.sections**: 사이드바에서 섹션별로 그룹화
- **navigation.expand**: 현재 페이지 섹션 자동 확장
- **navigation.top**: 긴 페이지에서 맨 위로 가기 버튼 표시
- **search.highlight**: 검색어를 결과에서 하이라이트
- **content.code.copy**: 코드 블록에 복사 버튼 추가

### 🧭 네비게이션 구조
```yaml
nav:
  - 홈: index.md                          # 메인 페이지
  - 지역 소개:                            # 드롭다운 메뉴
    - 개요: about/overview.md
    - 역사: about/history.md
    - 지리: about/geography.md
  - 관광 명소:
    - 자연 명소: attractions/nature.md
    - 문화 유적: attractions/culture.md
    - 체험 활동: attractions/activities.md
  # ... 기타 메뉴들
  - 🛠️ 개발자: CONTRIBUTE.md             # 개발자용 기여 가이드
```

#### 네비게이션 구조 설명
- **단일 페이지**: `- 제목: 파일경로.md`
- **드롭다운 메뉴**: 하위 항목들을 들여쓰기로 구성
- **아이콘**: 유니코드 이모지나 Material 아이콘 사용 가능
- **파일 경로**: `docs/` 폴더 기준 상대 경로

### 🔌 플러그인 설정
```yaml
plugins:
  - search:                               # 검색 플러그인
      lang: ko                            # 한국어 검색 지원
```

- **search**: 사이트 내 통합 검색 기능
- **lang: ko**: 한국어 형태소 분석을 통한 정확한 검색

### 📝 마크다운 확장 기능
```yaml
markdown_extensions:
  - admonition                            # 알림 박스 (!!! note, !!! tip 등)
  - pymdownx.details                      # 접을 수 있는 세부사항
  - pymdownx.superfences                  # 고급 코드 펜스
  - pymdownx.tabbed:                      # 탭 기능
      alternate_style: true               # 대체 탭 스타일
  - pymdownx.emoji:                       # 이모지 지원
      emoji_index: !!python/name:material.extensions.emoji.twemoji
      emoji_generator: !!python/name:material.extensions.emoji.to_svg
  - attr_list                             # HTML 속성 추가
  - md_in_html                            # HTML 내 마크다운 처리
```

#### 확장 기능 설명
- **admonition**: `!!! note "제목"` 형태의 알림 박스
- **pymdownx.details**: `??? "접힌 내용"` 형태의 접을 수 있는 요소
- **pymdownx.superfences**: 중첩된 코드 블록, 다이어그램 지원
- **pymdownx.tabbed**: `=== "탭명"` 형태의 탭 기능
- **pymdownx.emoji**: `:material-home:` 같은 아이콘 지원
- **attr_list**: `![이미지](path){ width="300" }` 같은 속성 추가
- **md_in_html**: HTML 태그 안에서 마크다운 사용 가능

### 🔧 추가 설정
```yaml
extra:
  social:                                 # 소셜 미디어 링크
    - icon: fontawesome/brands/facebook   # 페이스북 아이콘
      link: https://facebook.com/your-local-page
    - icon: fontawesome/brands/instagram  # 인스타그램 아이콘
      link: https://instagram.com/your-local-page
    - icon: fontawesome/solid/envelope    # 이메일 아이콘
      link: mailto:info@yourlocal.gov

copyright: Copyright &copy; 2024 우리 지역 관광청  # 저작권 표시
```

#### 소셜 미디어 설정
- **icon**: FontAwesome 또는 Material 아이콘 사용
- **link**: 해당 소셜 미디어 페이지 또는 연락처 링크
- 푸터에 아이콘으로 표시됨

### 🎯 설정 커스터마이징 팁

1. **색상 변경**
   ```yaml
   theme:
     palette:
       primary: blue        # 파랑계열로 변경
       accent: amber        # 강조색을 황색으로
   ```

2. **새 페이지 추가**
   ```yaml
   nav:
     - 새 섹션: new-page.md  # docs/new-page.md 파일 생성 필요
   ```

3. **언어 변경**
   ```yaml
   theme:
     language: en          # 영어로 변경
   plugins:
     - search:
         lang: en          # 영어 검색 지원
   ```

4. **기능 추가/제거**
   ```yaml
   theme:
     features:
       - navigation.instant    # 빠른 페이지 로딩 추가
       # - navigation.tabs     # 탭 네비게이션 제거 (주석 처리)
   ```

### ⚠️ 주의사항

- **YAML 문법**: 들여쓰기는 정확히 2칸 공백 사용
- **한글 인코딩**: 파일은 UTF-8로 저장
- **파일 경로**: `docs/` 폴더 기준 상대 경로 사용
- **아이콘 형식**: Material Icons 또는 FontAwesome 형식 준수
- **테스트**: 설정 변경 후 `mkdocs serve`로 테스트 필수

## 🚀 시작하기

### 필요 조건

- Python 3.7 이상
- pip (Python 패키지 관리자)

### 설치 방법

1. **저장소 클론**
   ```bash
   git clone https://github.com/your-username/local-promotion-site.git
   cd local-promotion-site
   ```

2. **필요한 패키지 설치**
   ```bash
   pip install -r requirements.txt
   ```

3. **개발 서버 실행**
   ```bash
   mkdocs serve
   ```

4. **브라우저에서 확인**
   - 주소: http://127.0.0.1:8000
   - 실시간 미리보기 지원 (파일 수정 시 자동 새로고침)

### 빌드 및 배포

1. **정적 사이트 빌드**
   ```bash
   mkdocs build
   ```

2. **GitHub Pages 배포**
   ```bash
   mkdocs gh-deploy
   ```

## 📝 콘텐츠 수정 가이드

### 페이지 추가
1. `docs/` 폴더에 새 마크다운 파일 생성
2. `mkdocs.yml`의 `nav` 섹션에 페이지 추가

### 이미지 추가
1. `docs/images/` 폴더에 이미지 파일 업로드
2. 마크다운에서 `![설명](images/파일명.jpg)` 형식으로 참조

### 설정 변경
- 사이트 제목, 설명: `mkdocs.yml`의 `site_name`, `site_description` 수정
- 네비게이션 구조: `mkdocs.yml`의 `nav` 섹션 수정
- 테마 색상: `mkdocs.yml`의 `theme.palette` 수정

## 🎨 커스터마이징

### 색상 테마 변경
```yaml
theme:
  palette:
    primary: blue  # 기본 색상
    accent: light blue  # 강조 색상
```

### 로고 추가
```yaml
theme:
  logo: images/logo.png
  favicon: images/favicon.ico
```

### 소셜 미디어 링크 수정
```yaml
extra:
  social:
    - icon: fontawesome/brands/facebook
      link: https://facebook.com/your-page
```

## 📱 반응형 디자인

이 사이트는 다양한 화면 크기에 최적화되어 있습니다:

- **모바일** (< 768px): 햄버거 메뉴, 세로 레이아웃
- **태블릿** (768px - 1024px): 적응형 그리드
- **데스크톱** (> 1024px): 전체 네비게이션, 사이드바

## 🔧 기술 스택

- **MkDocs**: 정적 사이트 생성기
- **Material for MkDocs**: 모던한 테마
- **Python Markdown**: 마크다운 처리
- **PyMdown Extensions**: 고급 마크다운 기능
- **GitHub Pages**: 호스팅 (선택사항)

## 📊 SEO 최적화

- 메타 태그 자동 생성
- 사이트맵 자동 생성
- 구조화된 데이터 지원
- 빠른 로딩 속도
- 모바일 친화적 디자인

## 🤝 기여하기

1. Fork 프로젝트
2. 새 브랜치 생성 (`git checkout -b feature/새기능`)
3. 변경사항 커밋 (`git commit -am '새 기능 추가'`)
4. 브랜치에 Push (`git push origin feature/새기능`)
5. Pull Request 생성

자세한 기여 방법은 [개발자 가이드](docs/CONTRIBUTE.md)를 참조하세요.

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 📞 문의

- **이메일**: info@ourlocal-tourism.go.kr
- **전화**: 02-1234-5678
- **웹사이트**: https://www.ourlocal-tourism.go.kr

## 🔄 업데이트 로그

### v1.0.0 (2024-01-15)
- 초기 사이트 구축
- 기본 페이지 구성 완료
- Material 테마 적용
- 반응형 디자인 구현

---

*우리 지역의 아름다움을 함께 나누어요!* ❤️ 