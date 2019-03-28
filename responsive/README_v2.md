# 반응형 웹

## Break Point(분기점, 중단점)
* 디바이스(mobile, tablet, web) 화면의 최소사이즈를 기준으로 정합니다. 
<pre>
Mobile : 320px(iPhone5)
Tablet : 712px(Galaxy Tab S4)
Web : 1280px(HD)
</pre>
> [디바이스별 화면 사이즈 목록](https://material.io/tools/devices/)

## 레이아웃

### 레이아웃의 흐름에 맞게 콘텐츠를 배치하자.
> 웹사이트에서 레이아웃이 구성되는 방식은 왼쪽에서 오른쪽으로 상단에서 하단으로 쌓이게 됩니다. [예제(codepen)](https://codepen.io/blythe4/pen/ZPZQLd)   
    * 웹부터 디자인을 시작한다면 모바일을 염려해두고 레이아웃의 흐름을 생각하면서(왼쪽에서 오른쪽으로, 상단에서 하단으로) 콘텐츠 배치

1. Break Point(mobile, tablet, web)별 콘텐츠 배치
    > 레이아웃의 흐름이 달라지지 말자.  
    * 흐름에 맞지 않는 레이아웃 [예시](http://developers.xeogen.com/blythe/responsive/flow/)  
        ** 참고 : Do it! 반응형 웹 만들기 예제 소스
        ![이미지](/img/layout.jpg)  
    * 흐름에 맞는 레이아웃 [예시](https://www.thinkwithgoogle.com/)

2. 고정영역 및 가변영역
    > Break Point에 따라 레이아웃의 넓이가 고정 또는 가변
    1. 고정영역 + 가변영역 [예제](https://www.w3schools.com/w3css/tryw3css_templates_portfolio.htm)  
    2. 가변영역 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cv.htm)  

3. Column(영역), Gutter(여백)
    > [예제(codepen)](https://codepen.io/blythe4/pen/MLjwYw/)
    - Column과 여백 둘 다 가변적으로 화면 넓이의 비율에 따라 변한다.
    - 여백은 고정이고, Column은 화면 넓이의 비율에 따라 변한다.

## Fullpage (화면에서 스크롤할 때 하나의 Section 단위로 이동하는 페이지)
> Fullpage는 화면에서 하나의 영역만 표시되고 스크롤 시 다음 또는 이전 영역이 표시되는 방식입니다.
* Web의 최소 해상도 1280x720(HD)으로 봤을 때 사용자마다 브라우저의 설정이 달라 화면의 높이는 최대 550px로 생각하고 디자인되어야 합니다. 화면에서 일부만 표시가 되고 해당 내용이 정확하게 전달되지 않을 수도 있게 됩니다.
* HD해상도 이상의 화면에서 콘텐츠는 수직 가운데 정렬이 되도록 합니다.

    <b>해상도</b>
    <pre>
    1. HD : 1280x720  
    2. FullHD : 1920x1080  
    3. QHD : 2560x1440  
    </pre>
[예시1 - 한국산업단지공단(반응형 O)](https://card.kicox.or.kr/main/main.do)  
[예시2 - 판토스(반응형 X)](http://www.pantos.com)

## 이미지  
> 모바일 디바이스에서 웹 페이지는 논리적 픽셀을 기준으로 마크업 하지만 이미지는 물리적 픽셀 기준 크기에 맞게 제작해야 합니다. 실제 화면에 보일 때는 물리적 픽셀 단위로 보이기 때문입니다. 현재 아이폰5의 픽셀 비율(Density)은 2배입니다. 따라서 논리적 픽셀 기준 크기의 가로세로 2배 크기로 이미지를 제작해야 합니다. 만약 픽셀 비율이 2인 디바이스에서 논리적 픽셀 기준으로 만든 이미지를 본다면 선명하지 않고 흐릿하게 보일 것입니다.

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

* [Density 설명](https://brunch.co.kr/@blackindigo-red/18)

### 주의사항  
> 디자이너가 물리적 픽셀 기준으로 가이드를 작성하면 퍼블리셔는 모든 픽셀 단위 숫자를 논리적 픽셀 기준으로 계산해 마크업합니다. 물리적 픽셀 기준으로 홀수인 값을 논리적 픽셀 기준으로 환산하면 소수점 아래에 숫자가 생기는데 이 값은 브라우저에 따라서 반올림하거나 버리므로 가이드와 동일하게 구현될 수 없습니다. 
> * 예를 들어 33px * 33px의 아이콘을 마크업 할 때 16px * 16px 이나 17px * 17px 둘 중 한 가지를 선택하여 코딩하게 됩니다.

** 참고 : 디자이너가 묻고 개발자가 답하는 웹 이야기

### 이미지를 어떻게 사용해야 할까?
> 픽셀 비율에 따른 2배 이상의 이미지를 사용하게 된다면 파일의 용량이 커지게되고 사이트 속도저하에 영향을 끼치게됩니다.  
> 벡터 이미지, [image sprite 사용](https://dev.zzoman.com/2017/11/29/image-sprite-vs-webpack-string/)
* SVG(벡터이미지) 사용 : 로고, 아이콘

### 이미지 표시 방법
1. 비율 따른 이미지 축소 및 확대  
![이미지](/img/image-01-01.jpg)  
2. 디바이스별로 이미지를 다르게 표현  
![이미지](/img/responsive-img.png)  
3. 높이를 고정으로 하고 이미지를 가운데로 정렬 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cafe.htm)

## 동영상
1. 화면에 꽉차게 표시(Background)  
    : 동영상을 가운데 정렬 [사이트 예제](http://sugentech.com/KOR/)  
    : 디바이스 화면의 비율에 따라 표시되어야 하는 동영상이 각각 필요합니다. 
    * 가로 보다 세로의 너비가 클 때(320x568)
    * 세로 보다 가로의 너비가 클 때(568x320)
2. 비율로 표시 [예제(codepen)](https://codepen.io/blythe4/pen/YgZPdY)  

## 폰트  
1. Mobile - 시스템 폰트 / Web - 웹폰트 사용  
    : 모바일에서 시스템 폰트 사용 [확인](http://developers.xeogen.com/blythe/responsive/) 필요
2. 폰트 크기
    * 폰트 크기 고정
    <pre>
    1. Mobile : 24px
    2. Tablet : 28px
    3. Web : 32px</pre>
    * Break point에 따른 폰트 크기 가변 [예제(codepen)](https://codepen.io/blythe4/pen/dagVRa)  
    <pre>
    1. Mobile : 7.5vw
    2. Tablet : 28px
    3. Web : 32px</pre>
> vw : 뷰포트 너비(Viewport Width)로 디바이스 화면의 넓이값을 기준으로 1/100 단위. 1vw는 viewport width의 1%와 같다.   
  예) 320px의 넓이일때 1vw는 3.2px이 된다.   
  ** vw로 사용할 경우 가로와 세로의 변화가 클수록 폰트 크기의 변화도 커진다.  
  ** 퍼블리싱 vmin TEST [caniuse 확인](https://caniuse.com/#search=vmin)  

### 폰트 사이즈가 가변적일 때 생길 수 있는 이슈는?
* 이미지 폰트의 크기는 고정이고, 시스템폰트는 가변이 될 때
* 제목이 있는 리스트 항목에서 제목과 내용이 한 줄에 표시되었을 때
(absolute로 띄어져 있을 때 padding이나 width에 대한 가변 값은?)
* 2개 이상의 column으로 되어 있을 때 320px 화면에서 폰트가 한 줄에 보일 때 [예제(codepen)](https://codepen.io/blythe4/pen/QoRgqp)

## 표 
> 모바일 디바이스 대응   
* [리스트 형태로 보기1](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [리스트 형태로 보기2](https://codepen.io/AllThingsSmitty/pen/MyqmdM)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))
* [슬라이드로 변환](https://medium.com/@andrejsabrickis/responsive-tables-made-simple-4609804ce60b)

## 리스트
* 리스트의 순서 및 정렬

### 순서가 있는 리스트
 [예제(codepen)](https://codepen.io/blythe4/pen/NoBWgo)

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
> [예제(codepen)](https://codepen.io/blythe4/pen/WPgvKX)

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


-----

[참고서적]
* Do it! 반응형 웹 만들기
* 디자이너가 묻고 개발자가 답하는 웹 이야기