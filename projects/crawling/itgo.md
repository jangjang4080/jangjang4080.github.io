---
layout: page
title: 셀레니움을 이용한 크롤러 - ITGo, Modenedu
---

<http://modenedu.com/>  
<http://itgo.co.kr/education/>  
해당 강좌의 비디오 정보를 가져온다. 
```python
class Constants:
    class_title = "introTxt"                    # 클래스 제목
    class_room_set = "class_room_set_dd"        # 클래스룸 정보
    class_article_list = "class_list3_dd"       # 아티클 리스트
    class_article = "strong"                    # 아티클 제목
    class_video_js_box = "video-js-box"         # 클래스 아이디
    tag_iframe = "iframe"                       # 프레임
    tag_video = "video"                         # 비디오 파일 링크
```
* 테스트 url
    * [HD]모바일 앱(어플) 개발자를 위한 Xamarin(자마린) 제대로 배우기 Part.3
        * 클래스룸 : http://modenedu.com/class/class_room.php?c_code=la_F060804
        * 샘플 영상 : http://modenedu.com/class/sample.php?sample=F060804
        * 강의 영상 : rtmp://mp.itgo.co.kr:1935/vod/D27CDB6E-AE6D-11cf-96B8-444553540000/F060804/01.mp4
    * [HD]인공지능(AI) 프로그래밍 - 파이썬을 활용한 Machine Learning(머신러닝), Deep Learning(딥러닝) 기초 다지기 Part.1
        * 클래스룸 : http://modenedu.com/class/class_room.php?c_code=la_F010304
        * 샘플 영상 : http://modenedu.com/class/sample.php?sample=F010304
        * 강의 영상 : rtmp://mp.itgo.co.kr:1935/vod/22D6f312-B0F6-11D0-94AB-0080C74C7E95/F010304/01.mp4

#### 명령어 인자
* 필수 인자
    * class code  
        예) <http://modenedu.com/class/class_room.php?c_code=la_F060804> 이 원하는 페이지라면 class code는 마지막에 la_F060804 또는 F060804 모두 가능
* 부가 인자
    * -start : 시작 아티클 인덱스, 지정하지 않았을 때 기본 1
    * -end : 끝 아티클 인덱스, 지정하지 않았을 때 기본 1

#### 사용예
* 에디터
```python
crawling("la_F060804", 1, -1)
```
* 터미널
```python
python3 itgo.py "la_F060804" -start 1 -end -1
```
* rtmpdump  
rtmpdump 만 따로 사용하기  
단, 비디오 파일의 url을 미리 알고 있어야 한다.
```python
rtmpdump -r "rtmp://mp.itgo.co.kr:1935/vod/D27CDB6E-AE6D-11cf-96B8-444553540000/F060804/01.mp4" -o "01.mp4"
```