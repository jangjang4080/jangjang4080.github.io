---
layout: page
title: ERP 관리자 웹 - 교육 출판 B2B 주문·유통 플랫폼
---

<img src='{{ "/assets/images/web/cedu-erp/icon.png" | relative_url }}' alt='relative' width="15%" height="15%">

교육 출판사의 B2B 주문·유통 업무(주문·반품·거래처·단가·매출)를 다루는 ERP 관리자 웹입니다. 본사·총판·선생님 3개 권한별로 메뉴와 화면이 분기되는 구조로, 서버 연동 전 단계에서 전 화면 퍼블리싱과 UI 인터랙션을 먼저 완성해 UX를 사전 검증하고, 서버 연동 시 그대로 이어받을 수 있는 코드 구조로 인계했습니다.

※ 화면의 데이터는 모두 더미 데이터이며, 클라이언트 정보 보호를 위해 텍스트를 블러 처리했습니다.

### 기술 스택
React, TypeScript, Vite, Tailwind CSS, React Router, Zod, Recharts

### 실행 환경
웹 데스크톱 (관리자 전용)

### 담당 작업
* 전 화면 퍼블리싱·UI 인터랙션 개발 (본사·총판·선생님 권한 분기 포함)
* 디자인 토큰 체계화, 공용 컴포넌트(테이블 셸·DatePicker·검색바·모달 등) 구축
* 더미 데이터 계약(zod)·API 레이어 분리 설계 및 인계 문서 작성

---

## 핵심 기능
* **대시보드·매출 통계** - KPI 카드에서 조건 필터가 걸린 목록으로 바로 이동, 매출 현황을 기간·채널·거래처·상품별로 전환해 조회
* **주문·반품 관리** - 주문 목록·상세, 본사·총판별 주문서 작성, 배송지(본점/지점) 자동 적용, 재고 부족 경고, 반품·교환 요청 처리
* **거래처·상품·단가 관리** - 거래처·지점, 상품, 특별단가 그룹 관리, 목록 검색·엑셀 다운로드·일괄 업로드
* **계정·권한·메세지함** - 권한별 계정 관리와 최초 로그인 약관 동의 플로우, 권한별 레이아웃이 분기되는 메세지함
* **목록 공통** - 필터·검색·정렬이 실제 반영되고 조회 조건이 URL에 보존되어 상세 진입 후 복귀해도 유지

## 실행 화면
<div class="screenshot-grid-wide" markdown="0">
  <img src='{{ "/assets/images/web/cedu-erp/1.png" | relative_url }}' alt='대시보드'>
  <img src='{{ "/assets/images/web/cedu-erp/2.png" | relative_url }}' alt='매출현황 통계'>
  <img src='{{ "/assets/images/web/cedu-erp/3.png" | relative_url }}' alt='주문 목록'>
  <img src='{{ "/assets/images/web/cedu-erp/4.png" | relative_url }}' alt='주문 상세'>
  <img src='{{ "/assets/images/web/cedu-erp/5.png" | relative_url }}' alt='반품/교환'>
  <img src='{{ "/assets/images/web/cedu-erp/6.png" | relative_url }}' alt='거래처관리'>
  <img src='{{ "/assets/images/web/cedu-erp/7.png" | relative_url }}' alt='상품관리'>
  <img src='{{ "/assets/images/web/cedu-erp/8.png" | relative_url }}' alt='특별단가그룹'>
  <img src='{{ "/assets/images/web/cedu-erp/9.png" | relative_url }}' alt='계정관리'>
  <img src='{{ "/assets/images/web/cedu-erp/10.png" | relative_url }}' alt='메세지함'>
</div>
