# ✅ 배포 체크리스트 (Deployment Checklist)

프로덕션 배포 전에 이 체크리스트를 확인하세요!

---

## 🔍 배포 전 확인사항

### 필수 항목
- [ ] `npm install` 완료
- [ ] `npm run build` 성공
- [ ] `dist` 폴더 생성 확인
- [ ] 로컬에서 `npm run preview`로 빌드 결과 확인
- [ ] 모든 페이지 및 섹션 정상 작동 확인
- [ ] 이미지 로딩 확인
- [ ] 폰트 로딩 확인
- [ ] 반응형 디자인 확인 (모바일/태블릿/데스크톱)

### 권장 항목
- [ ] 메타 태그 및 SEO 설정 확인
- [ ] 파비콘 추가
- [ ] Open Graph 이미지 설정
- [ ] 404 페이지 확인
- [ ] 브라우저 콘솔 에러 확인
- [ ] 성능 테스트 (Lighthouse)

---

## 🌐 배포 플랫폼별 체크리스트

### Vercel
- [ ] GitHub 저장소에 코드 푸시
- [ ] [vercel.com](https://vercel.com) 계정 생성
- [ ] 프로젝트 import
- [ ] 빌드 설정 확인:
  - Framework Preset: `Vite`
  - Build Command: `npm run build`
  - Output Directory: `dist`
- [ ] 환경 변수 설정 (필요시)
- [ ] 도메인 연결 (선택사항)
- [ ] SSL 인증서 자동 설정 확인

### Netlify
- [ ] GitHub 저장소에 코드 푸시
- [ ] [netlify.com](https://netlify.com) 계정 생성
- [ ] "Import from Git" 선택
- [ ] 빌드 설정 확인:
  - Build command: `npm run build`
  - Publish directory: `dist`
- [ ] `netlify.toml` 파일 확인
- [ ] 환경 변수 설정 (필요시)
- [ ] 도메인 연결 (선택사항)

### Cloudflare Pages
- [ ] GitHub 저장소에 코드 푸시
- [ ] Cloudflare 계정 생성
- [ ] Pages 프로젝트 생성
- [ ] 빌드 설정:
  - Build command: `npm run build`
  - Build output directory: `dist`
- [ ] 도메인 연결 (선택사항)

### GitHub Pages
- [ ] `vite.config.ts`에 `base` 경로 추가
- [ ] GitHub Actions 워크플로우 설정
- [ ] Repository Settings → Pages 활성화
- [ ] `gh-pages` 브랜치 설정

---

## 🔧 기술 체크리스트

### 코드 품질
- [ ] ESLint 에러 없음
- [ ] TypeScript 컴파일 에러 없음
- [ ] 사용하지 않는 import 제거
- [ ] console.log 제거
- [ ] TODO 주석 확인

### 성능
- [ ] 이미지 최적화
- [ ] 코드 스플리팅 확인
- [ ] Lazy loading 적용
- [ ] 번들 크기 확인

### 보안
- [ ] 환경 변수 적절히 사용
- [ ] API 키 노출 확인
- [ ] HTTPS 사용 확인

---

## 📱 테스트 체크리스트

### 기능 테스트
- [ ] 모든 링크 작동 확인
- [ ] 언어 전환 기능 (KR/EN)
- [ ] 예약하기 버튼 작동
- [ ] 지도 인터랙션
- [ ] SNS 링크 (Facebook, Instagram)
- [ ] 연락처 정보 정확성

### 브라우저 테스트
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] Edge
- [ ] Mobile Safari (iOS)
- [ ] Chrome Mobile (Android)

### 디바이스 테스트
- [ ] 데스크톱 (1920x1080)
- [ ] 노트북 (1366x768)
- [ ] 태블릿 (768x1024)
- [ ] 모바일 (375x667)
- [ ] 대형 모바일 (414x896)

---

## 🎯 성능 목표

### Lighthouse 점수
- [ ] Performance: 90+ 🎯
- [ ] Accessibility: 90+ ♿
- [ ] Best Practices: 90+ ✅
- [ ] SEO: 90+ 🔍

### 로딩 시간
- [ ] First Contentful Paint < 1.5s
- [ ] Largest Contentful Paint < 2.5s
- [ ] Time to Interactive < 3.0s

---

## 📝 배포 후 확인사항

### 즉시 확인
- [ ] 배포 URL 접속 확인
- [ ] 모든 페이지 로딩 확인
- [ ] 모바일 뷰 확인
- [ ] HTTPS 인증서 확인

### 24시간 내 확인
- [ ] Google Search Console 등록
- [ ] Google Analytics 설정 (선택)
- [ ] 실제 사용자 피드백 수집
- [ ] 에러 로그 모니터링

### 지속적 확인
- [ ] 주간 성능 모니터링
- [ ] 사용자 행동 분석
- [ ] 정기적인 의존성 업데이트
- [ ] 보안 패치 적용

---

## 🚨 문제 발생 시

### 빌드 실패
```bash
# 1. 의존성 재설치
rm -rf node_modules package-lock.json
npm install

# 2. 캐시 삭제
rm -rf node_modules/.vite
rm -rf dist

# 3. 다시 빌드
npm run build
```

### 배포 후 페이지 오류
- [ ] 브라우저 콘솔에서 에러 확인
- [ ] 네트워크 탭에서 실패한 요청 확인
- [ ] 환경 변수 설정 재확인
- [ ] 빌드 로그 확인

### 성능 문제
- [ ] Lighthouse 보고서 확인
- [ ] 번들 분석 (vite-bundle-visualizer)
- [ ] 이미지 최적화 검토
- [ ] CDN 사용 고려

---

## 📞 지원 및 문의

### 기술 지원
- **Vercel 문서**: https://vercel.com/docs
- **Netlify 문서**: https://docs.netlify.com
- **Vite 문서**: https://vitejs.dev

### 펜션 관련 문의
- **전화**: 031-584-5748
- **휴대폰**: 010-2206-5748
- **이메일**: sidezzz@naver.com

---

## ✨ 배포 완료!

모든 항목을 체크했다면 배포 준비 완료입니다! 🎉

```bash
# 최종 배포 명령어
npm run build
vercel --prod  # 또는 선택한 플랫폼
```

**축하합니다! 🚀 Jane Cooper - SANGREEN Pension 웹사이트가 라이브됩니다!**

---

_Last updated: 2026-01-08_
