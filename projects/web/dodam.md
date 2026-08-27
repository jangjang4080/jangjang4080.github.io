---
layout: page
title: 도담도담 웹 - 나와 아이의 다이어리 소개 페이지
---

<img src='{{ "/assets/images/web/dodam/icon.png" | relative_url }}' alt='relative' width="15%" height="15%">

육아 기록 다이어리 앱 [도담도담](/projects/app/dodam.html)을 소개하고 앱스토어·구글플레이 다운로드로 연결하는 랜딩 웹입니다. 파스텔 톤과 마스킹테이프 등 앱의 브랜드 아이덴티티를 웹에서도 그대로 이어받아, 검색이나 외부 링크로 처음 들어온 사용자가 서비스의 감성과 핵심 가치를 바로 이해할 수 있게 구성했습니다.

JSON-LD 구조화 데이터와 OG 메타태그로 검색·AI 검색 노출을 다듬고, Mixpanel·Clarity로 다운로드 버튼 클릭 등 사용자 행동을 추적해 전환율 분석 기반을 마련했습니다. 카카오톡·인스타그램 인앱 브라우저에서 스토어 리다이렉트가 실패하는 경우에는 fallback 팝업으로 이탈을 막았습니다.

### 기술 스택
React, TypeScript, Tailwind CSS, react-i18next, Vercel, Mixpanel, Clarity, JSON-LD

### 실행 환경
웹 데스크톱 / 모바일 (반응형)

### 담당 작업
* 기획, 디자인, 개발, 운영 전체 (자체 서비스)
* React 랜딩 웹 개발 및 반응형 대응
* SEO/AEO/GEO 최적화, JSON-LD 구조화 데이터 적용
* Mixpanel·Clarity 애널리틱스 도입, 인앱 브라우저 스토어 연결 대응
* Vercel 배포

---

## 핵심 기능
* **서비스 소개** - 주요 기능을 스크린샷과 함께 감성적인 톤으로 안내해 첫 방문자가 서비스를 빠르게 이해
* **스토어 다운로드 연결** - App Store·Google Play 다운로드 버튼과 인앱 브라우저 fallback 처리
* **다국어(i18n) 지원** - react-i18next 기반으로 언어 리소스를 분리해 코드 변경 없이 언어 추가 가능
* **반응형 웹** - 데스크톱과 모바일 모두에 맞춘 레이아웃과 사용자 경험
* **애널리틱스·SEO** - JSON-LD 구조화 데이터, OG 메타태그, 다운로드 전환 추적

## 웹 페이지
[https://bebeda.me](https://bebeda.me)

## 스토어
- [구글 플레이 스토어](https://play.google.com/store/apps/details?id=com.bebeda.bebeda)
- [애플 앱 스토어](https://apps.apple.com/app/id6758451103)

## 실행 화면
<div class="screenshot-grid-wide" markdown="0">
  <img src='{{ "/assets/images/web/dodam/1.png" | relative_url }}' alt='랜딩 히어로 - 나와 아이의 이야기 다운로드 섹션'>
  <img src='{{ "/assets/images/web/dodam/2.png" | relative_url }}' alt='도담도담이 특별한 이유 - 다이어리와 쉽고 예쁜 일상 기록 소개'>
  <img src='{{ "/assets/images/web/dodam/3.png" | relative_url }}' alt='가족 리뷰 - 사용자 후기와 에세이 소개'>
  <img src='{{ "/assets/images/web/dodam/4.png" | relative_url }}' alt='도담도담 활용하기 - 4가지 핵심 기능과 우체통 섹션'>
  <img src='{{ "/assets/images/web/dodam/5.png" | relative_url }}' alt='우체통 - 피드백 편지 작성 폼'>
  <img src='{{ "/assets/images/web/dodam/6.png" | relative_url }}' alt='모바일 랜딩 - 반응형 히어로 화면'>
</div>
