# 극소수 v1.1 Phase 1

회원 시스템과 개인 DB 기반의 첫 번째 Next.js 버전입니다.

## 포함 기능
- Supabase Auth 회원가입 / 로그인 / 로그아웃 등
- 경험 기록 생성 및 상세 보기
- Training 기록 생성 및 상세 보기
- 사용자별 데이터 격리 RLS
- Dashboard 최근 기록
- Phase 2 AI 평가 필드 준비

## 1. Supabase
1. Supabase 프로젝트 생성
2. SQL Editor에서 `supabase/schema.sql` 전체 실행
3. Project URL과 Publishable Key 확인

## 2. 환경변수
`.env.example`을 `.env.local`로 복사하고 값을 입력합니다.

```env
NEXT_PUBLIC_SUPABASE_URL=https://YOUR_PROJECT.supabase.co
NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY=YOUR_PUBLISHABLE_KEY
NEXT_PUBLIC_SITE_URL=http://localhost:3000
```

## 3. 로컬 실행
```bash
npm install
npm run dev
```

## 4. Supabase Auth URL
로컬
- Site URL `http://localhost:3000`
- Redirect URL `http://localhost:3000/auth/callback`

Vercel 배포 후
- Site URL `https://YOUR_DOMAIN.vercel.app`
- Redirect URL `https://YOUR_DOMAIN.vercel.app/auth/callback`

## 5. Vercel
- Framework Preset Next.js
- Root Directory 비움
- Build Command 기본값
- Output Directory 기본값
- Environment Variables에 Supabase URL, Publishable Key, NEXT_PUBLIC_SITE_URL 등록

## Phase 1 성공 기준
- 회원가입 및 로그인
- Experience 저장 후 상세 조회
- Training 저장 후 상세 조회
- 같은 계정으로 PC와 모바일에서 동일 데이터 확인
- 다른 계정에서는 타 사용자 데이터가 보이지 않음
