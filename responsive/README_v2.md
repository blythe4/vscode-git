# 반응형 웹

## Break Point(분기점, 중단점)
* 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 Break Point를 정한다. 
* Mobile 최소 사이즈 : iphone 5
* Tablet 최소 사이즈 : Tabs4
* Web 최소 사이즈 : HD 해상도 1280px
> [디바이스별 화면 사이즈 목록](https://material.io/tools/devices/)

<pre>
1. Mobile : 320px
2. Tablet : 712px
3. Web : 1280px
</pre>

## 모바일부터 기획, 디자인   
** 모바일부터 기획, 디자인이 되어야 하는 이유는?  
** 시안단계에서 웹부터 디자인을 하지만, 실제 프로젝트 진행 시 모바일부터 디자인  
** 콘텐츠의 흐름을 생각하면서(왼쪽에서 오른쪽으로, 상단에서 하단으로) 디자인을 하자.  
** 모바일을 염려해두고 웹부터 디자인 한다면 ...  

### 콘텐츠의 흐름에 맞춰 레이아웃을 배치하자.
* [콘텐츠의 흐름에 맞지 않은 레이아웃 예시](http://developers.xeogen.com/blythe/responsive/flow/)  
** 참고 : Do it! 반응형 웹 만들기 예제 소스
* [콘텐츠의 흐름에 맞는 레이아웃 예시](https://www.thinkwithgoogle.com/)

## 레이아웃  
> 가이드 제작시 레이아웃의 고정과 가변에 대한 내용을 psd에 표시

1. Break Point(모바일, 테블릿, 웹)별 구조가 달라질때 [LG화학 디지털아카이브 - 해외사업 히스토리](http://developers.xeogen.com/blythe/lgarchive/overseas.html)
    - 레이아웃의 흐름이 달라지지 말자. (왼쪽에서 오른쪽으로 → / 위에서 아래로 ↓)  
![이미지](/img/layout.jpg)  
2. 레이아웃 넓이 고정
    > Break Point에 따라 각각 레이아웃의 넓이가 고정 또는 가변적으로 변경 <a href="https://codepen.io/blythe4/pen/yZGXeo" target="_blank">CodePen 예제</a>
    1. 가변적인 레이아웃 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cv.htm)
    2. 고정적인 레이아웃 + 가변적인 레이아웃 [예제](https://www.w3schools.com/w3css/tryw3css_templates_portfolio.htm)  
3. 여백 
    > <a href="https://codepen.io/blythe4/pen/MLjwYw/" target="_blank">CodePen 예제</a>
    - 여백과 column의 넓이 둘다 가변적으로 화면 넓이의 비율에 따라 변한다.
    - 여백의 넓이는 항상 고정이고, column이 화면 넓이의 비율에 따라 변한다.

### Full Page(화면에서 스크롤할 때 하나의 Section 단위로 변하는 페이지) 반응형
* 화면에서 보여지는 내용이 화면보다 많을 경우 내용이 화면에서 다 안보이고 화면 밖으로 넘어가 스크롤이 생기거나 이미지 또는 내용이 겹쳐보이거나 짤려보일 수 있다.(비율에 맞춰 작게 보이거나 여백이 많아져 보일 수도 있다.)
* 해상도는 사용자마다 브라우저의 설정이 다르기 때문에 화면에 넘치거나, 여백이 많이 생길 수 도 있다.
* Web에서 Full Page로 하고 다른 디바이스에서 일반 스크롤이 되도록 한다.
* Web의 최소 높이 사이즈를 HD 해상도로 생각하고 사용자의 브라우저 설정에 따라서 100px ~ 200px정도 차이가 있어 컨텐츠의 높이는 최대 550px이 넘지 않도록 한다.
* Web에서 컨텐츠는 항상 화면의 가운에 정렬이 되도록 한다.

### 해상도
1. HD : 1280x720  
2. FullHD : 1920x1080  
3. QHD : 2560x1440  

[예제1 - 한국산업단지공단](https://card.kicox.or.kr/main/main.do)  
[예제2 - 판토스](http://www.pantos.com)

## 이미지 요소  
> 디바이스에 따라 화면의 밀도가 2배에서 4배로 점점 증가하고 있다.  
> 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이미지가 필요하다. 실제로 사용자들은 2배 이상의 이미지에 대해 큰 차이점을 느끼지 못하기 때문에 2배 이미지만으로 충분하다. (화면의 크기와 가시거리 내용 찾아서 추가하기)  

### 이미지를 어떻게 사용해야 할까?
> 파일의 용량이 커질수록 사이트의 속도저하에 영향을 끼친다.  
> PC 또는 노트북을 제외한 디바이스들의 밀도는 기본 1배 이상으로 이미지는 2배 이미지를 기본으로 사용하자.

1. SVG 사용 : 로고, 아이콘

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
    : 가로보다 세로의 너비가 클때 또는 세로보다 가로의 너비가 클때 표시되어야 하는 동영상이 각각 필요하다.
2. 동영상 비율로 표시  
    [예제1](https://getbootstrap.com/docs/4.0/utilities/embed/)
    [예제2](https://codepen.io/blythe4/pen/YgZPdY)  

## 폰트  
1. 모바일 - 시스템 폰트 / 웹 - 웹폰트 사용  
    : 모바일에서 시스템 폰트 사용 확인 중
2. 디바이스 넓이에 따라 폰트 크기 고정
    <pre>
    1. Web : 32px
    2. Tablet : 28px
    3. Mobile : 20px
    </pre>
3. 분기점 기준으로 디바이스 넓이에 따라 비율([vw 단위](https://www.w3schools.com/howto/howto_css_responsive_text.asp))로 사용
    <pre>
    1. Web : 32px
    2. Tablet : 28px
    3. Mobile : 5.55vw
    </pre>
4. 정해진 폰트 크기가 디바이스 화면 사이즈에 따라 비율로 확대,축소  
    : 제오젠 포트폴리오 제작 시 TEST 후 적용 여부 판단 예정
    [:root를 기준으로 상대단위 적용](https://allthingssmitty.com/2016/12/05/flexible-type-using-root/)
    * 아이폰5 일때 :root의 font-size는 10px이 된다.  
    <pre>
    화면 사이즈 : 320 x 568
    3.2px + 5.68px + 1.6px = 10.48px
    ( 1vw +  1vh  + .5vmin )
    </pre>
    
    ```css
    :root {
        font-size: calc(1vw + 1vh + .5vmin);
    }
    body {
       font: 1rem/1.6 sans-serif;
    }

    p {
       font-size: 1em;
    }
    @media screen and (max-width: 45em) {
        p {
            font-size: 1.25em;
        }
    }
    ```

> vw : Viewport Width로 디바이스의 스크린 넓이값을 기준으로 1vw는 viewport 넓이의 1%와 같다.  
  예) 320px의 넓이일때 1vw는 3.2px이 된다. [예제](https://codepen.io/blythe4/pen/dagVRa)

### 모바일에서 폰트 사이즈가 가변적일 때 생길 수 있는 이슈는?
* 이미지폰트의 크기는 고정인데 시스템폰트는 가변이 된다.
* 제목이 absolute로 띄어져 있을때 padding값이나 width값은 가변값에 대한 계산은?
    : rem단위 test 해보자
* 2개 이상의 column으로 되어 있을때 320px 화면에서 폰트가 한줄에 보여질때

## 표 
> 모바일 디바이스에서 대응 방법  
* [모바일에서 리스트 형태로 보기1](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [모바일에서 리스트 형태로 보기2](https://codepen.io/AllThingsSmitty/pen/MyqmdM)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))
* [모바일에서 슬라이드로 변환](https://medium.com/@andrejsabrickis/responsive-tables-made-simple-4609804ce60b)

## 리스트
* 리스트의 순서 및 정렬
> HTML 마크업시 리스트는 순서대로 나열되며 순차적으로 왼쪽부터 쌓이게 된다. 두개 이상의 column이 있다면 오른쪽부터 하나씩 아래로 붙게 된다. 

### 순서가 있는 리스트
 <a href="https://codepen.io/blythe4/pen/NoBWgo" target="_blank">CodePen 예제</a>

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
> <a href="https://codepen.io/blythe4/pen/WPgvKX" target="_blank">CodePen 예제</a>

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
    - 여백 넓이(가변, 고정)
    - column, gutter 넓이(가변, 고정)
    - 이미지(비율, 높이고정, 정렬, 위치)
    - 동영상(비율, 화면 Full, 정렬)
    - 폰트 크기(디바이스 넓이에 맞춰 가변적인 사이즈, 고정사이즈) : 확인 필요
    - GNB 메뉴 표시(Hover, Touch에 따라 GNB 표시) : 확인 필요

## 폴더구조 및 파일명
> 프로젝트 시작 전 기준을 정하고 공동 작업자들과 공유한다.  
> 하나의 폴더 안에 파일명으로 구분  
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
