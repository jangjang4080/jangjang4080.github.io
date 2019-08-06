---
layout: page
title: 맥스 스크립트, 블렌더 스크립트 등을 이용해 골프 코스 위성 데이터 리소스 전처리 프로세스 개발
---

골프 코스 위성 데이터의 이미지 크기가 너무 커서 3D 맥스 높이맵 불러오기를 이용하면 당시 왠만한 머신에서 메모리 부족 현상으로 느려지거나, 3D 맥스가 종료되는 일이 발생했습니다. 골프 그래픽 팀에 고성능 컴퓨터를 한 대 구입해 높이맵 생성, 랜더링, 전처리 등의 작업을 했지만, 다른 모델러들이 이 컴퓨터의 높이맵 생성 작업이 끝나길 기다려 다음 작업을 진행해야 했습니다. 모든 모델러들에게 고성능 컴퓨터를 구입해줄 수도 있지만, 이 작업만을 위해 컴퓨터를 구입하기도 애매했습니다. 

이를 프로그래밍으로 해결할 수 있을까 고민하다가 블렌더 높이맵 생성은 메모리 부족 현상이 일어나지 않는다는 것을 발견하고, 위성 데이터 -> 블렌더 -> 3D 맥스의 과정을 자동화하는 전처리 프로세스를 개발하게 되었습니다.  

## 개발 환경
* [Blender 2.55 64비트 r32738. built 2010-10-27](http://www.blender.org/download/get-blender/)
* [Python 2.7](http://python.org/download/)
* [Python Imaging Library 1.1.7 for Python 2.7](http://effbot.org/downloads/PIL-1.1.7.win32-py2.7.exe)
* [Wing IDE Editor](http://www.wingware.com/downloads/wingide)
* [ImageMagick](http://www.imagemagick.org/script/install-source.php#windows)

## 실행 환경
Windows  

---

## 프로젝트 설명
1. GIP(Golf Image Processor)
    * do_thumbnail(target_directory): - 지정된 디렉토리 하위 이미지 파일들을 일정 이하 사이즈로 줄여준다.
    * merge_select(target_directory, dest_directory, fileNames, thumb=False, channel16=False): - 이미지 파일들을 하나의 이미지로 합해준다.
2. GMP(Golf Mesh Preprocessor)
    * SCENE_GIP
        * run_gip(self, context): - thumbnail, merge 하는 작업을 수행한다.
        * run_ImageMagick_convert: - 16비트 이미지를 8비트로 만들어준다.
            * 사용하는 이유 : 블렌더에서 매핑에 16비트 이미지를 지원하지 않기 때문에
    * SCENE_AddHoleInfo
        * Invoke(self, context, event): - Add Hole Info 라는 버튼을 누르면 발생한다. 편집한 홀들의 정보를 저장해둔다.(메모리)
    * SCENE_EditHoleInfo
        * Invoke(self, context, event): - 왼쪽에 hole no 번호를 조정한 후 Edit 버튼을 누르면 발생한다. hole no 에 따라 이전에 편집한 홀들의 정보를 불러온다.
    * SCENE_Export – 홀 정보들을 파일로 출력한다. Ini 포멧 파일을 생성.
    * SCENE_GenerateCC – 파일 이름을 기반으로 row, clo을 파악해 블렌더 메시를 생성한다.

---

## 과정

![image](/assets/images/games/max_heightmap/gmp_look.png)

1. 해당 버전의 블렌더를 설치하고, addon으로 gmp를 설치한다.
2. Golf Mesh Preprocessor라는 addon이 생기는데 A의 CC Folder 라는 항목에 파일 경로를 설정할 수 있는 버튼이 있다. 이 버튼을 눌러 DEM, DSM, ORTHO_Tiles 폴더들이 있는 경로를 지정해주자. 주의점 – 경로가 제대로 설정되지 않는 경우 Accept, Relative Path라는 체크 박스의 체크를 해제해주자.
3. B의 GIP 버튼을 누르면 이미지 파일들의 thumbnail, merged 같은 일들을 수행한다.
4. C의 GenerateCC 버튼을 누르면 블렌더 Python API들을 이용해 해당 프로젝트 폴더의 파일 이름을 기준으로 메시를 생성해준다.
5. D의 ImportCC 버튼을 누르면 H의 Export 버튼을 통해 파일로 만들었던 ini 파일을 불러올 수 있다.
6. E의 hole no 를 조정해 F의 Edit 버튼을 누르면 원하는 홀의 선택 정보를 수정할 수 있다.
7. G의 Add Hole Info 버튼을 클릭하면 편집한 홀 선택 정보들이 E의 hole no 를 기준으로 저장된다.
8. H의 Export 버튼을 클릭하면 편집한 홀 선택 정보들이 ini 파일로 출력된다.

---

## 3D Max – 하이트맵(Displace map) 생성

![image](/assets/images/games/max_heightmap/GolfHoleEditor.png)

1. A - 블렌더를 통해 생성된 ini 파일이 들어있는 프로젝트 폴더를 선택해준다.
2. B – 전체 CC를 생성해준다.
3. C – 코스를 선택한다.
4. D – 홀을 선택한다.
5. E – 위에서 선택한 원하는 코스의 홀을 생성해준다.
6. F – 높이에 대한 strength
7. G – strength 적용
