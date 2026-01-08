# 배포 가이드 (Deployment Guide)

## 빠른 시작 (Quick Start)

이 프로젝트는 즉시 배포 가능한 상태입니다. 아래 방법 중 하나를 선택하세요.

## 🚀 방법 1: Vercel (가장 쉬움, 추천)

### A. GitHub를 통한 배포
1. 코드를 GitHub 저장소에 푸시
2. [vercel.com](https://vercel.com) 방문 및 가입
3. "New Project" 클릭
4. GitHub 저장소 선택
5. "Deploy" 클릭 - **완료!** 🎉

### B. CLI를 통한 배포
```bash
# Vercel CLI 설치
npm install -g vercel

# 배포
vercel

# 프로덕션 배포
vercel --prod
```

**배포 후 URL**: `https://your-project.vercel.app`

---

## 🌐 방법 2: Netlify

### A. GitHub를 통한 배포
1. 코드를 GitHub 저장소에 푸시
2. [app.netlify.com](https://app.netlify.com) 방문 및 가입
3. "Add new site" → "Import an existing project"
4. GitHub 저장소 선택
5. 빌드 설정 확인:
   - Build command: `npm run build`
   - Publish directory: `dist`
6. "Deploy site" 클릭 - **완료!** 🎉

### B. Drag & Drop 배포
```bash
# 로컬에서 빌드
npm run build

# dist 폴더를 Netlify에 드래그 앤 드롭
```

---

## 📦 방법 3: GitHub Pages

1. `vite.config.ts` 수정:
```typescript
export default defineConfig({
  base: '/your-repo-name/', // 저장소 이름으로 변경
  // ... 기존 설정
})
```

2. GitHub Actions 워크플로우 생성 (`.github/workflows/deploy.yml`):
```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          
      - name: Install dependencies
        run: npm install
        
      - name: Build
        run: npm run build
        
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

3. Repository Settings → Pages → Source를 "gh-pages" 브랜치로 설정

---

## ☁️ 방법 4: Cloudflare Pages

1. [dash.cloudflare.com](https://dash.cloudflare.com) 방문
2. "Pages" → "Create a project"
3. GitHub 저장소 연결
4. 빌드 설정:
   - Build command: `npm run build`
   - Build output directory: `dist`
5. "Save and Deploy"

---

## 🔥 방법 5: Firebase Hosting

```bash
# Firebase CLI 설치
npm install -g firebase-tools

# Firebase 로그인
firebase login

# 프로젝트 초기화
firebase init hosting

# 빌드
npm run build

# 배포
firebase deploy --only hosting
```

**firebase.json 설정**:
```json
{
  "hosting": {
    "public": "dist",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
}
```

---

## 📊 방법 6: AWS S3 + CloudFront

### 1. S3 버킷 생성 및 설정
```bash
# AWS CLI로 빌드 파일 업로드
npm run build
aws s3 sync dist/ s3://your-bucket-name --delete
```

### 2. CloudFront 배포 생성
- Origin: S3 버킷
- Default Root Object: `index.html`
- Error Pages: 404 → `/index.html` (SPA 라우팅용)

---

## ✅ 배포 전 체크리스트

- [ ] `npm install` 성공
- [ ] `npm run build` 성공
- [ ] 로컬에서 `dist` 폴더 생성 확인
- [ ] 환경 변수 설정 (필요한 경우)
- [ ] 도메인 연결 (선택사항)

---

## 🔧 문제 해결

### 빌드 오류
```bash
# node_modules 삭제 후 재설치
rm -rf node_modules package-lock.json
npm install
npm run build
```

### 폰트 로딩 문제
- 폰트는 Google Fonts에서 자동으로 로드됩니다
- 네트워크 연결 확인

### 이미지 로딩 문제
- 모든 이미지는 `figma:asset` 스킴을 사용합니다
- Figma Make 환경에서 자동으로 처리됩니다

---

## 📱 성능 최적화

빌드 후 자동으로 적용되는 최적화:
- ✅ 코드 압축 (Minification)
- ✅ Tree shaking
- ✅ CSS 최적화
- ✅ 이미지 최적화
- ✅ 코드 스플리팅

---

## 🌍 커스텀 도메인 연결

### Vercel
1. Project Settings → Domains
2. 도메인 입력 후 DNS 설정

### Netlify
1. Domain Settings → Add custom domain
2. DNS 레코드 설정

---

## 📞 지원

배포 관련 문제가 있나요?
- Vercel 문서: [vercel.com/docs](https://vercel.com/docs)
- Netlify 문서: [docs.netlify.com](https://docs.netlify.com)
- GitHub Issues: 프로젝트 저장소에 이슈 등록

---

**Happy Deploying! 🚀**
