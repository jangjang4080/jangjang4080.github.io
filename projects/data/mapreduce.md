---
layout: page
title: 하둡 맵리듀스
---

Hadoop MapReduce를 이용해 CIE DB 데이터를 가공합니다.  

## 1. 전처리
* MapReduce 시간을 줄이기 위해 분석을 위해 필요한 날짜 이전 db들 삭제

## 2. 맵리듀스 프로젝트
* Java 언어로 코드 작성
* MongoDB Connector for Hadoop 라이브러리 이용

## 3. 하둡 머신에서 맵리듀스 실행
* 2번에서 준비한 jar 파일을 하둡 머신에 전송한 후 yarn 명령어를 이용해 맵리듀스 작업을 실행  
![image](/assets/images/data/1.png)
* MapReduce 작업을 모두 수행하고 JobHistory에서 확인

## 4. DB 확인
* MapReduce 결과가 MongoDB에 제대로 쓰기되었는지 확인