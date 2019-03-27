# 반응형 웹

## Break Point(분기점, 중단점)
* 디바이스(web, tablet, mobile) 화면의 최소사이즈를 기준으로 Break Point를 정한다. 
* Mobile 최소 사이즈 : iPhone5(320px)
* Tablet 최소 사이즈 : TabS4(712px)
* Web 최소 사이즈 : HD 해상도(1280px)
> [디바이스별 화면 사이즈 목록](https://material.io/tools/devices/)

## 레이아웃  
> 가이드 제작시 레이아웃의 고정과 가변에 대한 내용을 PSD에 표시

### 모바일부터 기획, 디자인  
** 웹사이트에서 레이아웃이 구성되는 방식은 왼쪽에서 오른쪽으로 상단에서 하단으로 쌓이게 된다.[예제](https://codepen.io/blythe4/pen/ZPZQLd)   
** 시안단계에서 웹부터 디자인을 하지만, 실제 프로젝트 진행 시 모바일부터 디자인을 했으면 좋겠습니다.  
** 만일 웹부터 디자인을 시작해야 한다면 모바일을 염려해두고 콘텐츠의 흐름을 생각하면서(왼쪽에서 오른쪽으로, 상단에서 하단으로) 디자인을 하자

### 레이아웃의 흐름에 맞게 콘텐츠를 배치하자.
1. Break Point(모바일, 테블릿, 웹)별 구조가 달라질때
    - 레이아웃의 흐름이 달라지지 말자. (왼쪽에서 오른쪽으로 → / 위에서 아래로 ↓)  
![이미지](/img/layout.jpg)  

* [흐름에 맞지 않는 레이아웃 예시](http://developers.xeogen.com/blythe/responsive/flow/)  
** 참고 : Do it! 반응형 웹 만들기 예제 소스
* [흐름에 맞는 레이아웃 예시](https://www.thinkwithgoogle.com/)

2. 레이아웃의 고정영역 및 가변영역
    > Break Point에 따라 각각 레이아웃의 넓이가 고정 또는 가변적으로 변경
    1. 고정영역 + 가변영역 [예제](https://www.w3schools.com/w3css/tryw3css_templates_portfolio.htm)  
    2. 가변영역 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cv.htm)
3. Column(영역), Gutter(여백)
    > [CodePen 예제](https://codepen.io/blythe4/pen/MLjwYw/)
    - Column과 여백 둘다 가변적으로 화면 넓이의 비율에 따라 변한다.
    - 여백은 고정이고, Column은 화면 넓이의 비율에 따라 변한다.

### Fullpage(화면에서 스크롤할 때 하나의 Section 단위로 변하는 페이지) 반응형
* Fullpage는 화면에서 하나의 영역만 표시되고 스크롤시 다음영역이 표시되는 방식입니다.
* Web의 최소 해상도 1280x720으로 봤을때 사용자마다 브라우저의 설정이 달라 화면의 높이는 최대 550px로 생각하고 표시되어야 합니다. 1080px높이를 기준으로 표시 했을때 720px화면의 사용자들은 해당 내용의 1/3만 표시가 되고 해당 내용이 정확하게 전달 되지 않을 수도 있게 됩니다.
* 해상도는 사용자마다 브라우저의 설정이 다르기 때문에 화면에 넘치거나, 여백이 많이 생길 수 도 있다.
* Web의 최소 높이 사이즈를 HD 해상도로 생각하고 사용자의 브라우저 설정에 따라서 100px ~ 200px정도 차이가 있어 컨텐츠의 높이는 최대 550px이 넘지 않도록 한다.
* Web에서 Fullpage로 하고 다른 디바이스에서 일반 스크롤이 되도록 한다.
* Web에서 컨텐츠는 항상 화면의 수직 가운데 정렬이 되도록 한다.

#### 해상도
<pre>
1. HD : 1280x720  
2. FullHD : 1920x1080  
3. QHD : 2560x1440  
</pre>
[예제1 - 한국산업단지공단(반응형 O)](https://card.kicox.or.kr/main/main.do)  
[예제2 - 판토스(반응형 X)](http://www.pantos.com)

## 이미지 요소  
> 모바일 기기에서 웹 페이지는 논리적 픽셀을 기준으로 마크업하지만 이미지는 물리적 픽셀 기준 크기에 맞게 제작해야 합니다. 실제 화면에 보일 때는 물리적 픽셀 단위로 보이기 때문입니다. 현재 아이폰 5의 픽셀 비율은 2입니다. 따라서 논리적 픽셀 기준 크기의 가로세로 2배 크기로 이미지를 제작해야 합니다. 만약 픽셀 비율이 2인 기기에서 논리적 픽셀 기준으로 만든 이미지를 본다면 선명하지 않고 흐릿하게 보일 것입니다.

|    구분   |물리적해상도|논리적해상도|픽셀비율(Density)|
|:---------:|:----------:|:----------:|:---------------:|
|아이폰x    |  1125x2436 |   375x812  |        3        |
|아이폰6+,7+|  1080x1920 |   414x736  |        3        |
|아이폰6,7  |  750x1334  |   375x667  |        2        |
|아이폰5    |  640x1136  |   320x568  |        2        |
|갤럭시s8   |  1440x2960 |   360x740  |        4        |
|갤럭시s6,s7|  1440x2560 |   360x640  |        4        |
|갤럭시s5   |  1080x1920 |   360x640  |        3        |
|LG G3,G4,G5|  1440x2560 |   360x640  |        4        |

[화면 크기 확인 사이트](http://mydevice.io/)

### 주의사항  
> 웹 디자이너가 물리적 픽셀 기준으로 마크업 가이드를 작성하면 마크업 개발자는 모든 픽셀 단위 숫자를 논리적 픽셀 기준으로 환산해 마크업합니다. 물리적 픽셀 기준으로 홀수인 값을 논리적 픽셀 기준으로 환산하면 소수점 아래에 숫자가 생기는데 이 값은 브라우저에 따라서 반올림하거나 버리므로 마크업 가이드와 동일하게 구현될 수 없습니다. 
> * 예를 들어 33px * 33px의 아이콘을 퍼블리싱 할때 16px * 16px 이나 17px * 17px 둘 중 한가지를 선택하여 코딩하게 된다.

* [사람이 보는 크기의 인식](https://brunch.co.kr/@ultra0034/23)
* [DP, PT](https://brunch.co.kr/@eeasily/17)
* [640시안](https://front8062.tistory.com/27)

### 이미지를 어떻게 사용해야 할까?
> 파일의 용량이 커질수록 사이트의 속도저하에 영향을 끼친다.  
> 벡터 이미지, [image sprite 사용](https://dev.zzoman.com/2017/11/29/image-sprite-vs-webpack-string/)
* SVG(벡터이미지) 사용 : 로고, 아이콘

### 이미지 표시 방법
1. 비율 따른 이미지 축소 및 확대  
![이미지](/img/image-01-01.jpg)  
2. 디바이스별로 이미지를 다르게 표현  
![이미지](/img/responsive-img.png)  
3. 높이를 고정으로 하고 이미지를 가운데로 정렬 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cafe.htm)

## 동영상
> 동영상이 Background에서 자동재생+loop일때 
1. 화면에 꽉차게 표시  
    : 동영상을 가운데 정렬 [사이트 예제](http://sugentech.com/KOR/)  
    : 디바이스 화면의 비율에 따라 가로보다 세로의 너비가 클때(320x568) 또는 세로보다 가로의 너비가 클때(568x320) 표시되어야 하는 동영상이 각각 필요하다.
2. 동영상 비율로 표시 [예제](https://codepen.io/blythe4/pen/YgZPdY)  

## 폰트  
1. 모바일 - 시스템 폰트 / 웹 - 웹폰트 사용  
    : 모바일에서 시스템 폰트 사용 확인 중
2. 폰트 크기 고정
    <pre>
    1. Mobile : 24px
    2. Tablet : 28px
    3. Web : 32px
    </pre>
* Break point에 따른 폰트 크기 가변([vw 단위](https://www.w3schools.com/howto/howto_css_responsive_text.asp))
    <pre>
    1. Mobile : 7.5vw
    2. Tablet : 28px
    3. Web : 32px
    </pre>
> vw : 뷰포트 너비(Viewport Width)로 디바이스 화면의 넓이값을 기준으로 1/100 단위. 1vw는 viewport width의 1%와 같다. 
  예) 320px의 넓이일때 1vw는 3.2px이 된다. [예제](https://codepen.io/blythe4/pen/dagVRa)  
  ** vw로 사용할 경우 가로와 세로의 변화가 클수록 폰트 크기의 변화도 커진다  
  ** 퍼블리싱 vmin TEST 예정  

### 폰트 사이즈가 가변적일 때 생길 수 있는 이슈는?
* 이미지폰트의 크기는 고정이고, 시스템폰트는 가변이 될때
* 제목이 있는 리스트 항목에서 제목과 내용이 한줄에 표시되었을때
(absolute로 띄어져 있을때 padding이나 width에 대한 가변값은?)
* 2개 이상의 column으로 되어 있을때 320px 화면에서 폰트가 한줄에 보여질때[예제](https://codepen.io/blythe4/pen/QoRgqp)

## 표 
> 모바일 디바이스에서 대응 방법  
* [모바일에서 리스트 형태로 보기1](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [모바일에서 리스트 형태로 보기2](https://codepen.io/AllThingsSmitty/pen/MyqmdM)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))
* [모바일에서 슬라이드로 변환](https://medium.com/@andrejsabrickis/responsive-tables-made-simple-4609804ce60b)

## 리스트
* 리스트의 순서 및 정렬

### 순서가 있는 리스트
 [CodePen 예제](https://codepen.io/blythe4/pen/NoBWgo)

<pre>
01. List  02.List  03. List  04.List  05. List  06.List  
</pre>

```html
<ul>
    <li>01. List</li>
    <li>02. List</li>
    <li>03. List</li>
    <li>04. List</li>
    <li>05. List</li>
    <li>06. List</li>
</ul>
```

### 제목이 포함 된 리스트 
> [CodePen 예제](https://codepen.io/blythe4/pen/WPgvKX)

* Mobile 일때
<pre>
제목
내용내용내용내용내용내용내용

제목
내용내용내용내용내용내용내용내용

제목
내용내용내용내용내용내용내용
</pre>

* Tablet, PC 일때
<pre>
제목 | 내용내용내용내용내용
제목 | 내용내용내용내용내용내용내용
제목 | 내용내용내용내용내용내용
</pre>

------

## Break Point 별 가이드 표시 내용
    - 레이아웃 고정 넓이(Left menu)
    - column, gutter 넓이(가변, 고정)
    - 이미지(비율, 높이고정, 정렬, 위치)
    - 동영상(비율, 화면 Full, 정렬)
    - 폰트 크기(디바이스 넓이에 맞춰 가변적인 사이즈:Mobile대응, 고정사이즈)
    - GNB 메뉴 표시(Hover, Touch에 따라 GNB 표시):확인 필요

------
## 폴더구조 및 파일명  
1. 폴더구조  
    : IA를 따른다.
<pre>
- main
- about
- product
- contact
...
</pre>
2. 파일명  
    : SB에 있는 pageID로 정한다.  
    : 공통(가이드)은 0번째로 한다.  
    : 디바이스 구분은 _Sufix로 구분한다.(w - PC / t - Tablet / m - Mobile)
<pre>
- 00_Guide.psd
- U01_01_001_m.psd
- U01_01_001_t.psd
- U01_01_001_w.psd
- U01_01_002_m.psd
- U01_01_002_t.psd
- U01_01_002_w.psd
</pre>
