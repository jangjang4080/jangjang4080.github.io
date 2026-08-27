---
layout: page
title: 도담도담 어드민 - 운영·모더레이션·AI 프롬프트 관리자 웹
---

<img src='{{ "/assets/images/web/dodam-admin/icon.png" | relative_url }}' alt='relative' width="15%" height="15%">

육아 기록 다이어리 앱 [도담도담](/projects/app/dodam.html)의 운영 관리자 콘솔입니다. 지표 모니터링, 회원 관리, 커뮤니티 모더레이션, 다국어 콘텐츠 운영, AI 프롬프트 검증까지 서비스 운영 전반을 한 화면에서 처리합니다.

운영 초기에는 지표를 DB 조회와 여러 도구에 나눠 확인해야 했고, 신고·제재 처리나 앱 문구 수정도 개발자가 직접 손대야 했습니다. 이 과정을 운영자가 직접 처리할 수 있게 옮기고, AI 출력물은 픽스처 케이스로 눈으로 확인하며 모델을 비교할 수 있게 만들었습니다.

※ 화면의 사용자 정보는 개인정보 보호를 위해 블러 처리했습니다.

### 기술 스택
React 19, React Router v7, TypeScript, Vite, Tailwind CSS, TanStack Query, Axios, React Hook Form, Zod, Recharts, Pino, Playwright, Vercel

### 실행 환경
웹 데스크톱 (관리자 전용)

### 담당 작업
* 어드민 기획 (운영 흐름, 지표 정의, 모더레이션·제재 정책 설계)
* React Router v7 라우팅·인증 가드, JWT 자동 갱신 Axios 인터셉터 설계
* TanStack Query 기반 서버 상태 관리와 공용 UI 컴포넌트 체계 구축
* 지표 대시보드·회원 드릴다운·모더레이션·AI 프롬프트 운영 화면 개발

---

## 핵심 기능
* **통합 운영 대시보드** - 누적 사용자·일기 지표와 일·주·월·커스텀 기간 카드, 서버 latency·DB·차단 IP 등 시스템 상태, 사용자 피드백과 탈퇴 요청 처리까지 한 화면에서 확인
* **사용자·자녀 드릴다운** - 회원에서 자녀, 일기, 수면·식사·배변, 수업, 스티커 컬렉션·배치, 도담 나무까지 자녀 단위 활동을 깊이 있게 탐색
* **커뮤니티 모더레이션** - 신고 콘텐츠 모니터링, 블라인드 처리와 복구, 기간별 사용자 제재(3일·7일·영구)까지 운영 워크플로를 일원화
* **다국어 콘텐츠·앱 설정 관리** - 위로 메시지(KO/EN), 월별 꾸미기 테마, 스티커 카탈로그 362종, 앱 내 정적 페이지를 운영자가 배포 없이 직접 편집
* **AI 프롬프트 라이브러리·픽스처 테스트** - 일기·수면·식사·배변·주간 편지 프롬프트를 라이브러리화하고, 픽스처 케이스로 anthropic·openai·gemini를 같은 입력으로 비교 검증

## 실행 화면
<div class="screenshot-grid-wide" markdown="0">
  <img src='{{ "/assets/images/web/dodam-admin/1.png" | relative_url }}' alt='대시보드 - 누적/월·주·일·커스텀 기간 지표와 시스템 상태 모니터링'>
  <img src='{{ "/assets/images/web/dodam-admin/2.png" | relative_url }}' alt='회원 목록 - 검색·상태·Internal 필터'>
  <img src='{{ "/assets/images/web/dodam-admin/3.png" | relative_url }}' alt='회원 상세 - 자녀 정보·권한·알림 설정과 누적 활동'>
  <img src='{{ "/assets/images/web/dodam-admin/4.png" | relative_url }}' alt='공감탭 콘텐츠 모니터링 - 게시글/댓글 신고·인기·상태별 관리'>
  <img src='{{ "/assets/images/web/dodam-admin/5.png" | relative_url }}' alt='블라인드 콘텐츠 관리 - 정상 복구 또는 사용자 제재 처리'>
  <img src='{{ "/assets/images/web/dodam-admin/6.png" | relative_url }}' alt='사용자 제재 등록 - 3일/7일/영구 정지 기간 선택'>
  <img src='{{ "/assets/images/web/dodam-admin/7.png" | relative_url }}' alt='위로 메시지 관리 - 공감탭 메시지 KO/EN 다국어 편집'>
  <img src='{{ "/assets/images/web/dodam-admin/8.png" | relative_url }}' alt='사용자 피드백 - 카테고리별 피드백과 디바이스/앱 버전 정보'>
  <img src='{{ "/assets/images/web/dodam-admin/9.png" | relative_url }}' alt='탈퇴 요청 - 사유·소스·상태별 탈퇴 처리 이력'>
  <img src='{{ "/assets/images/web/dodam-admin/10.png" | relative_url }}' alt='스티커 도감 - 362개 카탈로그와 다국어 이름 관리'>
  <img src='{{ "/assets/images/web/dodam-admin/11.png" | relative_url }}' alt='꾸미기 관리 - 월별 테마와 폰트 타입 매핑'>
  <img src='{{ "/assets/images/web/dodam-admin/12.png" | relative_url }}' alt='앱 페이지 관리 - 앱 내 정적 페이지(소개/약관/개인정보)'>
  <img src='{{ "/assets/images/web/dodam-admin/13.png" | relative_url }}' alt='AI 프롬프트 라이브러리 - 픽스처 케이스 테스트와 모델 비교'>
</div>
