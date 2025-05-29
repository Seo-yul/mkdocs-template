# 기여 가이드 (CONTRIBUTE.md)

우리 지역 홍보 사이트 프로젝트에 기여해주셔서 감사합니다! 이 가이드는 프로젝트 구성, 실행 방법, 그리고 기여 방법에 대한 상세한 정보를 제공합니다.

## 📋 목차

- [프로젝트 개요](#프로젝트-개요)
- [개발 환경 설정](#개발-환경-설정)
- [프로젝트 구조](#프로젝트-구조)
- [로컬 실행 방법](#로컬-실행-방법)
- [개발 워크플로우](#개발-워크플로우)
- [콘텐츠 작성 가이드](#콘텐츠-작성-가이드)
- [코드 스타일 가이드](#코드-스타일-가이드)
- [기여 방법](#기여-방법)
- [문제 해결](#문제-해결)

## 🌟 프로젝트 개요

이 프로젝트는 MkDocs와 Material 테마를 사용하여 제작된 지역 관광 홍보 사이트입니다.

### 기술 스택
- **MkDocs 1.5.0+**: 정적 사이트 생성기
- **Material for MkDocs 9.4.0+**: 모던한 반응형 테마
- **Python Markdown**: 마크다운 처리 엔진
- **PyMdown Extensions**: 고급 마크다운 확장 기능

### 주요 특징
- 한국어 지원 및 SEO 최적화
- 반응형 디자인 (모바일/태블릿/데스크톱)
- 다크/라이트 모드 지원
- 실시간 검색 기능
- 소셜 미디어 통합

## 🛠️ 개발 환경 설정

### 필수 요구사항
- **Python**: 3.7 이상
- **pip**: Python 패키지 관리자
- **Git**: 버전 관리

### 1. 저장소 클론
```bash
# HTTPS로 클론
git clone https://github.com/your-username/local-promotion-site.git

# 또는 SSH로 클론
git clone git@github.com:your-username/local-promotion-site.git

# 프로젝트 디렉토리로 이동
cd local-promotion-site
```

### 2. 가상환경 설정 (권장)
```bash
# 가상환경 생성
python -m venv venv

# 가상환경 활성화 (Windows)
venv\Scripts\activate

# 가상환경 활성화 (macOS/Linux)
source venv/bin/activate
```

### 3. 의존성 패키지 설치
```bash
# requirements.txt로 일괄 설치
pip install -r requirements.txt

# 또는 개별 설치
pip install mkdocs>=1.5.0
pip install mkdocs-material>=9.4.0
pip install pymdownx-extensions>=10.0.0
pip install markdown>=3.4.0
```

### 4. 설치 확인
```bash
# MkDocs 버전 확인
mkdocs --version

# 사용 가능한 명령어 확인
mkdocs --help
```

## 📁 프로젝트 구조

```
local-promotion-site/
├── mkdocs.yml              # MkDocs 설정 파일
├── requirements.txt        # Python 의존성 패키지
├── README.md              # 프로젝트 개요
├── CONTRIBUTE.md          # 기여 가이드 (이 파일)
└── docs/                  # 문서 소스 파일들
    ├── index.md          # 홈페이지
    ├── contact.md        # 연락처 페이지
    ├── about/            # 지역 소개
    │   ├── overview.md   # 개요
    │   ├── history.md    # 역사
    │   └── geography.md  # 지리
    ├── attractions/      # 관광 명소
    │   ├── nature.md     # 자연 명소
    │   ├── culture.md    # 문화 유적
    │   └── activities.md # 체험 활동
    ├── food/            # 맛집 & 특산품
    │   ├── restaurants.md # 지역 맛집
    │   └── specialties.md # 특산품
    ├── events/          # 축제 & 이벤트
    │   ├── festivals.md  # 연중 축제
    │   └── seasonal.md   # 계절별 이벤트
    └── travel/          # 교통 & 숙박
        ├── transportation.md # 교통 안내
        └── accommodation.md  # 숙박 시설
```

### 주요 파일 설명

#### `mkdocs.yml`
- 사이트 메타데이터 (제목, 설명, 저자)
- 테마 설정 (색상, 폰트, 기능)
- 네비게이션 구조
- 플러그인 및 확장 기능 설정

#### `docs/` 디렉토리
- 모든 마크다운 콘텐츠 파일
- 이미지, CSS, JavaScript 등 정적 자산
- 각 폴더는 사이트의 주요 섹션을 나타냄

## 🚀 로컬 실행 방법

### 1. 개발 서버 시작
```bash
# 기본 포트(8000)에서 실행
mkdocs serve

# 다른 포트에서 실행
mkdocs serve --dev-addr=127.0.0.1:8001

# 외부 접속 허용
mkdocs serve --dev-addr=0.0.0.0:8000
```

### 2. 브라우저에서 확인
- 기본 주소: http://127.0.0.1:8000
- 실시간 리로드: 파일 수정 시 자동 새로고침
- 개발자 도구: F12로 반응형 디자인 테스트

### 3. 빌드 및 배포
```bash
# 정적 사이트 빌드
mkdocs build

# 빌드 파일 확인
ls -la site/

# GitHub Pages 배포
mkdocs gh-deploy

# 빌드 파일 정리
mkdocs build --clean
```

## 🔄 개발 워크플로우

### 1. 브랜치 전략
```bash
# 새로운 기능 브랜치 생성
git checkout -b feature/새로운-기능

# 버그 수정 브랜치 생성
git checkout -b bugfix/버그-설명

# 콘텐츠 업데이트 브랜치 생성
git checkout -b content/페이지-이름
```

### 2. 개발 과정
1. **이슈 확인**: GitHub Issues에서 작업할 내용 확인
2. **브랜치 생성**: 적절한 브랜치명으로 새 브랜치 생성
3. **로컬 개발**: `mkdocs serve`로 실시간 미리보기하며 개발
4. **테스트**: 다양한 화면 크기에서 테스트
5. **커밋**: 의미 있는 단위로 커밋
6. **Push & PR**: 원격 저장소에 푸시 후 Pull Request 생성

### 3. 테스트 체크리스트
- [ ] 모바일 디바이스에서 정상 표시
- [ ] 태블릿에서 레이아웃 확인
- [ ] 데스크톱에서 네비게이션 동작
- [ ] 다크/라이트 모드 전환 확인
- [ ] 검색 기능 동작 확인
- [ ] 모든 링크 정상 작동
- [ ] 이미지 로딩 확인

## 📝 콘텐츠 작성 가이드

### 마크다운 문법
```markdown
# 제목 1 (페이지 제목용)
## 제목 2 (주요 섹션용)
### 제목 3 (하위 섹션용)

**굵은 글씨** 또는 __굵은 글씨__
*기울임 글씨* 또는 _기울임 글씨_

- 순서 없는 목록
1. 순서 있는 목록

[링크 텍스트](URL)
![이미지 설명](이미지 경로)

`인라인 코드`

```
코드 블록
```
```

### Material 확장 문법

#### 알림 박스 (Admonitions)
```markdown
!!! note "참고"
    중요한 정보를 강조할 때 사용합니다.

!!! tip "팁"
    유용한 팁을 제공할 때 사용합니다.

!!! warning "주의"
    주의사항을 알릴 때 사용합니다.

!!! success "성공"
    성공 사례나 추천 사항에 사용합니다.

!!! info "정보"
    추가 정보를 제공할 때 사용합니다.
```

#### 탭 (Tabs)
```markdown
=== "탭 1"
    첫 번째 탭의 내용입니다.

=== "탭 2"
    두 번째 탭의 내용입니다.

=== "탭 3"
    세 번째 탭의 내용입니다.
```

#### 표 (Tables)
```markdown
| 컬럼 1 | 컬럼 2 | 컬럼 3 |
|--------|--------|--------|
| 데이터 1 | 데이터 2 | 데이터 3 |
| 데이터 4 | 데이터 5 | 데이터 6 |
```

#### 아이콘
```markdown
:material-home: 홈 아이콘
:fontawesome-solid-star: 별 아이콘
:octicons-heart-16: 하트 아이콘
```

### 이미지 추가 방법
1. `docs/images/` 폴더에 이미지 파일 업로드
2. 마크다운에서 참조: `![설명](images/파일명.jpg)`
3. 이미지 크기 조절: `![설명](images/파일명.jpg){ width="300" }`

## 🎨 코드 스타일 가이드

### 마크다운 스타일
- **제목**: 한국어와 영문 사이에 공백 없음
- **목록**: 일관된 들여쓰기 사용 (2칸 또는 4칸)
- **링크**: 설명적인 링크 텍스트 사용
- **이미지**: 의미 있는 alt 텍스트 작성

### YAML 설정 (mkdocs.yml)
- **들여쓰기**: 2칸 공백 사용
- **문자열**: 특수문자 포함 시 따옴표 사용
- **주석**: 섹션별로 명확한 주석 추가

### 파일명 규칙
- **소문자 사용**: 모든 파일명은 소문자
- **하이픈 사용**: 단어 구분 시 하이픈(-) 사용
- **의미 있는 이름**: 파일 내용을 명확히 나타내는 이름

## 🤝 기여 방법

### 1. Issue 생성
버그 리포트나 기능 제안 시:
```markdown
## 문제 설명
간단하고 명확한 문제 설명

## 재현 방법
1. 첫 번째 단계
2. 두 번째 단계
3. 문제 발생

## 예상 결과
어떤 결과를 예상했는지

## 실제 결과
실제로 어떤 일이 일어났는지

## 환경 정보
- OS: [예: macOS 13.0]
- 브라우저: [예: Chrome 108]
- Python: [예: 3.9.0]
```

### 2. Pull Request 가이드라인

#### PR 제목 형식
```
[타입] 간단한 설명

예시:
[Feature] 새로운 관광지 페이지 추가
[Bugfix] 모바일 네비게이션 수정
[Content] 맛집 정보 업데이트
[Style] CSS 스타일 개선
```

#### PR 설명 템플릿
```markdown
## 변경 사항
- 변경된 내용 1
- 변경된 내용 2
- 변경된 내용 3

## 관련 Issue
Closes #이슈번호

## 테스트 체크리스트
- [ ] 로컬에서 정상 빌드 확인
- [ ] 모바일 화면에서 테스트
- [ ] 검색 기능 동작 확인
- [ ] 링크 정상 작동 확인

## 스크린샷 (필요시)
변경 사항을 보여주는 스크린샷
```

### 3. 커밋 메시지 규칙
```
타입: 간단한 설명

상세한 설명 (필요시)

타입:
- feat: 새로운 기능
- fix: 버그 수정
- docs: 문서 수정
- style: 코드 스타일 변경
- refactor: 코드 리팩토링
- test: 테스트 추가/수정
- chore: 기타 작업

예시:
feat: 축제 정보 페이지 추가

사계절 축제 정보를 포함한 새로운 페이지를 추가했습니다.
- 벚꽃 축제 정보
- 단풍 축제 정보
- 겨울 빛 축제 정보
```

## 🐛 문제 해결

### 자주 발생하는 문제

#### 1. 포트 충돌 문제
```bash
# 에러: Address already in use
# 해결: 다른 포트 사용
mkdocs serve --dev-addr=127.0.0.1:8001
```

#### 2. 패키지 설치 오류
```bash
# 캐시 정리 후 재설치
pip cache purge
pip install -r requirements.txt --force-reinstall
```

#### 3. 한글 인코딩 문제
```bash
# Windows에서 한글 파일명 문제 해결
set PYTHONIOENCODING=utf-8
mkdocs serve
```

#### 4. 이미지 로딩 실패
- 이미지 경로 확인: `docs/images/` 폴더 내 위치
- 파일명 대소문자 정확히 입력
- 지원 형식 확인: JPG, PNG, GIF, SVG

### 로그 확인 방법
```bash
# 자세한 로그 출력
mkdocs serve --verbose

# 빌드 시 경고 메시지 확인
mkdocs build --strict
```

## 📞 도움 요청

### 문의 채널
- **GitHub Issues**: 버그 리포트, 기능 제안
- **GitHub Discussions**: 일반적인 질문, 아이디어 논의
- **이메일**: info@ourlocal-tourism.go.kr

### 자주 묻는 질문 (FAQ)

**Q: 새로운 페이지를 어떻게 추가하나요?**
A: `docs/` 폴더에 마크다운 파일을 생성하고, `mkdocs.yml`의 `nav` 섹션에 추가하세요.

**Q: 테마 색상을 변경할 수 있나요?**
A: `mkdocs.yml`의 `theme.palette` 섹션에서 `primary`와 `accent` 색상을 변경할 수 있습니다.

**Q: 다국어 지원은 어떻게 하나요?**
A: 현재는 한국어만 지원하며, 다국어 지원을 위해서는 mkdocs-static-i18n 플러그인을 사용할 수 있습니다.

---

## 📋 체크리스트

기여하기 전에 다음 사항들을 확인해주세요:

### 개발 환경
- [ ] Python 3.7+ 설치 확인
- [ ] 가상환경 활성화
- [ ] 필요한 패키지 설치 완료
- [ ] 로컬 서버 정상 실행

### 콘텐츠 작성
- [ ] 마크다운 문법 올바르게 사용
- [ ] 한국어 맞춤법 검사 완료
- [ ] 이미지 alt 텍스트 작성
- [ ] 링크 정상 작동 확인

### 테스트
- [ ] 모바일에서 정상 표시
- [ ] 태블릿에서 레이아웃 확인
- [ ] 데스크톱에서 네비게이션 확인
- [ ] 다크/라이트 모드 동작 확인

### 제출
- [ ] 의미 있는 커밋 메시지 작성
- [ ] PR 템플릿 작성 완료
- [ ] 관련 Issue 연결
- [ ] 리뷰어 지정

---

*함께 만들어가는 아름다운 지역 홍보 사이트에 기여해주셔서 감사합니다!* 🙏 