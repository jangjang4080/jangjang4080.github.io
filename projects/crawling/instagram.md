---
layout: page
title: 셀레니움을 이용한 크롤러 - Instagram
---

<https://www.instagram.com>  
이미지, 비디오, 글, 태그, 좋아요, 시간 등의 정보를 가져온다.
```python
class Constants:
    class_id = "AC5d8"                  # 아이디
    class_title = "rhpdm"               # 제목
    class_info = "g47SY "               # 게시물, 팔로워, 팔로우
    class_profile_img = "_6q-tv"        # 프로필 이미지
```
* 테스트 url
    * imvely_jihyun
    * yejinhand
    * leagueoflegends
    * explore/tags/제주중문맛집

#### 명령어 인자
* 필수 인자
    * sub url : base url 뒤에 붙을 url
        예) <https://www.instagram.com/leagueoflegends> 이 원하는 페이지라면 sub url은 leagueoflegends
* 부가 인자
    * -start : 시작 아티클 인덱스, 지정하지 않았을 때 기본 1
    * -end : 끝 아티클 인덱스, 지정하지 않았을 때 기본 1
    * -save : 이미지나 비디오 등을 저장할지에 대한 옵션, 기본 정보들은 info.csv에 저장

#### 사용예
* 에디터
    * 태그 검색
```python
crawling("explore/tags/제주중문맛집", 1, 50, False);
```
    * 아이디
```python
crawling("leagueoflegends", 1, -1, True);
```
* 터미널
    * 태그 검색
```python
python3 insta_deep.py "explore/tags/제주중문맛집" -start 1 -end 50
```
    * 아이디
```python
python3 insta_deep.py "leagueoflegends" -start 1 -end 50 -save
``` 
* 한 개 게시물 테스트 : 게시물의 URL을 직접 입력
```python
crawling_one_article("p/BiQdI11HoPU/");
```