# Jane Cooper - SANGREEN Pension 웹사이트

경기도 가평에 위치한 산그린 펜션의 모던한 공식 웹사이트입니다.

## 주요 기능

- **메인 히어로 섹션**: Jane Cooper 브랜딩과 예약 정보
- **객실 목록 (Room List)**: 다양한 객실 타입 소개와 갤러리
- **특별 시설 (Special)**: 메인 수영장 등 부대시설 상세 안내
- **관광 명소 (Tour Spot)**: 주변 관광지 정보 및 인터랙티브 지도
- **반응형 디자인**: 데스크톱 및 모바일 최적화
- **언어 선택**: 한국어/영어 전환 기능

## 기술 스택

- **React** 18.3.1 - UI 프레임워크
- **TypeScript** - 타입 안전성
- **Tailwind CSS** 4.x - 유틸리티 기반 스타일링
- **Vite** 6.3.5 - 차세대 빌드 도구
- **Material-UI** - UI 컴포넌트 라이브러리

## 설치 및 실행

### 개발 서버 실행
```bash
npm install
npm run dev
```

개발 서버가 시작되면 브라우저에서 `http://localhost:5173`으로 접속하세요.

### 프로덕션 빌드
```bash
npm run build
```

빌드된 파일은 `dist` 폴더에 생성됩니다.

### 빌드 미리보기
```bash
npm run preview
```

## 배포 방법

### 1. Vercel 배포 (권장)
[Vercel](https://vercel.com)은 React 애플리케이션을 위한 최적의 배포 플랫폼입니다.

**방법:**
1. GitHub에 코드를 푸시합니다
2. [Vercel](https://vercel.com)에 가입하고 "New Project" 클릭
3. GitHub 저장소를 import
4. 설정은 자동으로 감지됩니다 (Framework Preset: Vite)
5. "Deploy" 클릭
6. 몇 분 안에 배포 완료! (예: `https://your-project.vercel.app`)

**자동 배포:**
- main 브랜치에 push하면 자동으로 프로덕션에 배포
- PR을 만들면 미리보기 URL 자동 생성

### 2. Netlify 배포
[Netlify](https://netlify.com)도 훌륭한 선택입니다.

**방법:**
1. [Netlify](https://app.netlify.com)에 가입
2. "Add new site" → "Import an existing project" 선택
3. GitHub 저장소 연결
4. 빌드 설정:
   - **Build command**: `npm run build`
   - **Publish directory**: `dist`
5. "Deploy site" 클릭

### 3. GitHub Pages
무료로 GitHub에서 직접 호스팅할 수 있습니다.

**방법:**
1. `vite.config.ts`에 base 경로 추가:
   ```ts
   export default defineConfig({
     base: '/your-repo-name/',
     // ... 기존 설정
   })
   ```
2. 빌드 후 `dist` 폴더를 `gh-pages` 브랜치로 푸시
3. Repository Settings → Pages에서 활성화

### 4. 기타 호스팅 플랫폼
- **AWS S3 + CloudFront**: 엔터프라이즈급 배포
- **Firebase Hosting**: Google 클라우드 기반
- **Cloudflare Pages**: 빠른 글로벌 CDN
- **Render**: 간편한 설정

모든 플랫폼에서 `dist` 폴더의 정적 파일을 서빙하면 됩니다.

## 프로젝트 구조

```
├── src/
│   ├── app/
│   │   ├── App.tsx              # 메인 애플리케이션
│   │   └── components/          # 재사용 가능한 컴포넌트
│   ├── imports/
│   │   ├── 0작업-5-1053.tsx    # Figma 디자인 컴포넌트
│   │   └── svg-3nmr1onppt.ts   # SVG 아이콘들
│   └── styles/
│       ├── fonts.css            # 폰트 정의
│       ├── theme.css            # 테마 변수
│       └── tailwind.css         # Tailwind 설정
├── package.json
├── vite.config.ts
└── README.md
```

## 사용된 폰트

- **Noto Sans KR** - 한국어 본문
- **Nanum Gothic** - 한국어 헤딩
- **Inter** - 영문 텍스트
- **Baloo Bhai 2** - 장식용
- **Noto Sans** - 보조 폰트

## 환경 요구사항

- **Node.js** 18.x 이상
- **npm** 또는 **pnpm**

## 성능 최적화

✅ 이미지 최적화 (Figma asset 자동 압축)  
✅ 코드 스플리팅  
✅ Tree shaking  
✅ CSS 최소화  
✅ Lazy loading  

## 브라우저 지원

- Chrome (최신 2개 버전)
- Firefox (최신 2개 버전)
- Safari (최신 2개 버전)
- Edge (최신 2개 버전)

## 문의사항

### 펜션 예약 및 문의
- **주소**: 경기도 가평군 조종면 현등사길 35-9, 산그린펜션
- **대표**: 이엽
- **전화**: 031-584-5748
- **휴대폰**: 010-2206-5748
- **이메일**: sidezzz@naver.com

### 개발 관련 문의
이슈가 있으면 GitHub Issues에 등록해주세요.

## 라이선스

Copyright ⓒ SANGREEN Pension. All rights reserved.

---

**Made with ❤️ using Figma Make**
