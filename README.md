# ✨ UNSE — 오늘의 운세

> 사주 · MBTI · 혈액형 · 별자리 · 띠를 종합한 AI 운세 앱

![Preview](https://img.shields.io/badge/status-live-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue)

## 🔮 기능

- 5가지 데이터 기반 AI 종합 운세 분석
- 카테고리별 점수 (재물·연애·건강·전체기운)
- 💬 카카오톡 나에게 보내기 / 친구 공유
- 🔔 매일 알림 설정 (브라우저 푸시)
- MZ 감성 다크 UI, 모바일 최적화

## 🚀 배포 방법

### 1단계 — GitHub 저장소 생성

```bash
# 1. GitHub에서 새 저장소 생성 후
git init
git add .
git commit -m "✨ Initial commit: UNSE fortune app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/unse-app.git
git push -u origin main
```

### 2단계 — Vercel 배포

**방법 A: Vercel 웹사이트 (추천)**
1. [vercel.com](https://vercel.com) 접속 → GitHub 로그인
2. **"Add New Project"** 클릭
3. `unse-app` 저장소 선택 → **"Import"**
4. Framework Preset: **"Other"** 선택
5. **"Deploy"** 클릭 → 완료! 🎉

**방법 B: Vercel CLI**
```bash
npm i -g vercel
vercel login
vercel --prod
```

### 3단계 — 카카오 API 키 설정

1. [developers.kakao.com](https://developers.kakao.com) 접속
2. **내 애플리케이션 → 앱 추가**
3. 앱 이름: `UNSE운세`, 사업자명 입력
4. **앱 키 → JavaScript 키** 복사
5. Vercel 대시보드 → **Settings → Environment Variables** 추가:
   - 또는 `index.html`의 `YOUR_KAKAO_JS_KEY` 직접 교체

```javascript
// index.html 내 수정
const KAKAO_APP_KEY = '발급받은_JavaScript_키_입력';
```

6. 카카오 앱 설정 → **플랫폼 → Web** 추가:
   - 사이트 도메인: `https://your-app.vercel.app`

## 📁 프로젝트 구조

```
unse-app/
├── index.html      # 메인 앱 (모든 코드 포함)
├── vercel.json     # Vercel 배포 설정
├── .gitignore      # Git 무시 파일
└── README.md       # 이 파일
```

## ⚙️ 환경 설정

| 항목 | 값 |
|------|-----|
| Claude API | `claude-sonnet-4-20250514` |
| Kakao SDK | `2.7.2` |
| 배포 플랫폼 | Vercel (Static) |
| 프레임워크 | Vanilla JS (의존성 없음) |

## 🔧 카카오 매일 자동 발송 업그레이드

완전 자동 카카오톡 발송을 원한다면:

1. **카카오 채널** 개설 (카카오톡 채널 관리자센터)
2. **알림톡 API** 신청 (카카오 비즈니스)
3. **Vercel Cron Jobs** 또는 별도 서버에서 매일 스케줄 실행

```
매일 오전 8시 → 서버에서 Claude API 호출 → 카카오 알림톡 발송
```

## 📄 License

MIT © 2025 UNSE
