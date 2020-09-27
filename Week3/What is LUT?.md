# What is LUT?

+ LUT(Look Up Table)이란 어떤 자료나 정보를 찾기 위한 목록표.
+ 실제 컴퓨터의 처리과정에서 연산의 횟수를 줄이고 속도를 높이기 위해 미리 연산한 결과 값들을 저장한 후 이를 이용하여 처리하기 위한 배열 혹은 메모리의 집합을 지칭.
+ LUT는 다른 프로젝트에 사용되거나 적용될 수 있는 색상 등급을 생성하고 절약하는 데 가장 일반적으로 사용된다.
+ 포토샵의 컬러 룩업 테이블이란 이미지의 색상을 새롭게 해석하여 색감을 바꾸고 다양한 변화를 규칙화 한 것.
  + 원리는 색상의 기본값인 RGB의 무수히 많은 입력값을 다른 새로운 색상표에 대응하여 다른 색감으로 출력하는 방식.
  + 룩업 테이블을 통해 색보정 가능. 
  + 세 개의 1d 룩업 테이블 대신, 조금 더 (채도감소(desaturation)와 같은) 세련된 색 변환이 가능해지는 3d 룩업 테이블 하나를 사용.

-----------------------------------------------

## LUT가 전면화된 배경

+ 디지털 카메라로 영화를 만들던 초창기에는 이 룩업테이블에 대한 이슈는 크게 주목을 받지 못했다.
+ 초기의 디지털 카메라는 리니어 기반으로 카메라 제조사에서 이미 만들어 놓은 이미지 처리과정을 거친 결과물을 얻어냈기 때문.
+ 보다 넓은 다이내믹 레인지와 계조를 갖고 있는 영상을 얻고자 하면서 log란 개념 및 기술이 도입되었다.
+ 다양한 룩을 보다 빠르고 쉽게 적용하고 변화시키면서, 그 결과를 보다 정확하게 확인하기 위해서 사용되는 것이 바로 LUT. 
+ 최근 LUT는 이미지 편집 툴에서 사용되는 플러그인처럼 만들어져 일부 사용자들은 LUT을 컬러 필터처럼 여기면서 활용.

+ LUT는 당신의 영상을 평가할 수 있는 능력을 가진 어떤 프로그램에서도 사용될 수 있다. 
+ __가장 인기 있는 것은 어도비 프리미어 프로, 블랙매직 다빈치 리졸브, 파이널 컷이다. 포토샵에 LUT를 탑재해 스틸 이미지에 적용할 수도 있다.__
 
 ----------------------------
 
## LUT의 종류

#### 1. 1D LUT

+ R, G, B의 채널은 각각 하나의 1차원의 배열을 지니고 있다.
다시 말해 1D LUT는 1차원이기 때문에 개념상 면이 아닌 선 혹은 곡선의 형태이며 R, G, B 채널당 각각 커브를 움직일 수 있다. 
+ 1D LUT의 특징은 Lift, Gamma, Gain, Contrast에 1:1로 매칭이 되고, Hue, Saturation의 보정 값은 1D LUT에 아무런 변화를 주지 못한다. 
+ 이러한 결과로 인해 흔히들 __1D LUT를 흔히 밝기 값만 보정한다고 해서 ‘휘도 곡선’이라고 표현하고 있다.__

<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/1D_LUT_1a.png" width="400" height="300"><img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/1D_LUT_2a.png" width="400" height="300">

#### 2. 3D LUT

+ 3D LUT는 색상 채널의 모든 값 범위에 대한 색상 변환을 나타내는 각각의 축을 사용하여 선으로만 표현이 가능한 1D LUT와 달리 3차원 좌표계(3D Cube)로 시각화할 시킬 수 있다. 
+ R, G, B 각 축을 따라 있는 점의 개수는 LUT의 사이즈에 따라 다르게 생성된다.
+ 그 점을 중심으로 각각의 색상 채널에 대한 색상 변환을 할 수 있으며, 점 과 점 사이는 보간법을 이용해 근사치 값으로 보정이 되므로 LUT의 사이즈가 클수록 좀 더 정밀하게 색상을 컨트롤 할 수 있다.
+ 현재 우리가 LUT라고 통칭해서 부르고 많이 사용하는 LUT가 바로 3D LUT이다.

<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/3D_LUT_2X2X2.png" width="300" height="200"><img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/3D_LUT_3X3X3.png" width="300" height="200">
<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/3D_LUT_10X10X10.png" width="300" height="200"><img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/3D_LUT_33X33X33.png" width="300" height="200">

## 3. LUT의 포맷

+ 모든 LUT의 기능은 같지만 모든 LUT가 범용적으로 사용이 가능한 것은 아니다. 
+ LUT를 사용하는 장비나 소프트웨어마다 자신의 LUT의 포맷을 다르게 설정하고 있기 때문에 그 형식에 맞추어 사용해야만 정상적으로 작동이 가능하다.
+ 아래 목록표는 다양한 장비와 프로그램에서 사용되는 1D LUT, 3D LUT 포맷을 정리한 것이다.

 |1D LUTs|3D LUT|
 |----|----| 
 |DaVinci Resolve 1D Cube LUT (.cube)|DaVinci Resolve 3D Cube LUT (.cube)| 
 |Nucoda CMS 1D LUT (.cms)|Autodesk 3D  LUT (.3dl)|
 |DaVinci Resolve 1D LUT (.ilut, .olut)|FSI 3D LUT (.dat)|
 |Discreet 1D LUT (.lut)|Amira Look (.aml)|
 |Arri Look 1D tonemap (.xml)|Panasonic VLT 3D LUT (.vlt)|
 |                            | CTL LUT (.ctl)|
 |                            | Nucoda CMS 3D LUT (.cms)|
 |                            | Quantel 3D LUT (.txt)|
 |                            | DVS Clipster 3D LUT (.xml, .txt)|
 |                            | DaVinci 3D LUT (.davlut)|
 |                            | Resolve DAT 3D LUT (.dat)|
 |                            | Iridas Look (.look)|
 |                            | LightIllusion MatchLight 3D LUT (.mlc)|
 |                            | Unwrapped Texture LUT Image (.tiff)|
 |                            | CMS Test Pattern LUT Image (.tiff)|
 |                            | Hald CLUT Image (.tiff)|
                  
---------------------------
 
## LUT 만들기

+ __LUT는 자신이 필요해 의해서 만들어 쓰는 것도 가능.__ 
+ 만드는 방법은 무척이나 다양 - 후반 작업용 소프트웨어나 DI 툴, 이미지 편집 툴을 이용할 수도 있고 전문 LUT 제작 툴을 사용 할 수도 있다.           

##### 1. CMS 테스트 패턴
+ CMS 테스트 패턴에 대입해 LUT를 만드는 방법이 가장 손쉬운 방법. 
+ 보정이 끝난 이 후 LUT를 생성 할 때 사용자가 필요로 하는 툴에서 사용이 가능하도록 LUT 포맷만 맞추어 주면 어디서든 사용이 가능.
+ CMS라는 단어는 Color Management System의 약어이며 만들어 낼 수 있는 모든 색값을 입력 장치가 읽을 수 있도록 일정한 패턴을 만든 후 색값을 받아서서 데이터화 하는 작업을 지칭.
+ LUT를 만들 때 사용되는 이미지 패턴은 툴마다 CMS패턴 혹은 LUT패턴 등의 다양한 이름으로 제공되고 있다.
+ LUT의 사이즈에 따라서 색을 보정 할 수 있는 패턴의 크기와 수가 다르다. 
+ 당연한 것이겠지만 LUT의 사이즈가 크면 클 수록 색 보정을 할 수 있는 범위가 촘촘해지기 떄문에 더 정밀하게 색을 보정 할 수 있다.
+ CMS 패턴 이미지에 색보정 값을 적용 시켜 이 패턴을 가지고 LUT를 만드는 방법이 있다.

— LUT 사이즈에 따라 다르게 나타나는 CMS 테스트 패턴

2X2X2
<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/CMS_2X2X2.jpg" width="300" height="200">

3X3X3
<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/CMS_3X3X3.jpg" width="300" height="200">

10X10X10
<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/CMS_10X10X10.jpg" width="300" height="200">

33X33X33
<img src="http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/CMS_33X33X33.jpg" width="300" height="200">

##### 2. Photoshop: Export Color Table
+ 포토샵을 이용하면 외부의 LUT를 불러와 포토샵 안에서 적용시키는 것은 물론 자체적으로 색보정한 이미지를 기반으로 LUT를 생성한 후 외부의 다른 영상에도 LUT를 적용을 할 수 있다. 
+ 포토샵은 LUT 사이즈가 무려 256X256X256까지 지원이 될 정도는 엄청난 성능을 자랑한다.
+ 포토샵에서 출력하는 LUT 포맷은 3dl, csp, cube, icc 4가지이다.

LUT 파일을 불러올 수 있다.

![(http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Photoshop_LUT_1.png)](http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Photoshop_LUT_1.png)

LUT 출력 창

![(http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Photoshop_LUT_2.png)](http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Photoshop_LUT_2.png)

##### 3. Davinci Resolve: Generator LUT
+ 다빈치 리졸브에서는 Color페이지에서 프라이머리 색보정을 한 클립을 선택한 후 보조 버튼을 클릭해 보조 메뉴를 띄우게 되면 다빈치 리졸브용 .cube 포맷과 파나소닉용 .vlt LUT를 생성할 수 있다.
+ 생성 시 다빈치 리졸브의 LUT폴더가 기본으로 열리고 이 곳에 LUT를 저장할 경우 프로그램의 재실행 없이 바로 작업에 활용이 가능하다.

Davinci Resolve에서 LUT 생성하기

![(http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Davinci-Resolve%EC%97%90%EC%84%9C-LUT-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0.png)](http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Davinci-Resolve%EC%97%90%EC%84%9C-LUT-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0.png)

Davinci Resolve에서 LUT 적용

![(http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Davinci-Resolve%EC%97%90%EC%84%9C-LUT-%EC%A0%81%EC%9A%A9.jpg)](http://keruluke.com/archived_web/kft/wp-content/uploads/2015/06/Davinci-Resolve%EC%97%90%EC%84%9C-LUT-%EC%A0%81%EC%9A%A9.jpg)



-----------------------------------------------

참조

http://keruluke.com/archived_web/kft/vol4/lookuptable/
