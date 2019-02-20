# 반응형 제작
### Break Point 별 표시 내용
    - 레이아웃 고정 넓이(Left menu)
    - 여백 넓이(고정, 넓이 비율)
    - column, gutter 넓이(고정, 넓이 비율)
    - 이미지(비율, 높이고정, 밀도에 따른 배수 이미지)
    - 동영상(비율, 화면 Full, 정렬)
    - 폰트 크기(디바이스 넓이에 맞춰 가변적인 사이즈, 고정사이즈)
    - GNB 메뉴 표시(Hover, Touch에 따라 GNB 표시)
-----
## 1. Break Point(분기점, 중단점)
* 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 Break Point를 정한다. 
> [디바이스별 화면 사이즈 목록](https://material.io/tools/devices/)
<pre>
1. Mobile : 320px
2. Tablet : 712px
3. Web : 1280px
</pre>

## 2. 모바일 기준 기획, 디자인   
** 시안단계에서 웹부터 디자인을 하지만, 실제 프로젝트 진행 시 모바일부터 디자인

## 3. 폴더구조 및 파일명
> 프로젝트 시작 전 기준을 정하고 공동 작업자들과 공유한다. 
1. Break Point를 기준으로 폴더명 생성
    <pre>
    Web
    - 00.main.psd
    - ...
    Tablet
    - 00.main.psd
    - ...
    Mobile
    - 00.main.psd
    - ...
    </pre>
2. 하나의 폴더 안에 파일명으로 구분  
    <pre>
    PSD
    - 00.main_W.psd 또는 00.main_1280.psd
    - 00.main_T.psd 또는 00.main_712.psd
    - 00.main_M.psd 또는 00.main_320.psd
    </pre>

## 4. 레이아웃  
1. 각 디바이스(모바일, 테블릿, 웹)별 구조가 달라질때 [LG화학 디지털아카이브 - 해외사업 히스토리](http://developers.xeogen.com/blythe/lgarchive/overseas.html)
![이미지](/img/layout.jpg)  
2. 여백 
    > <a href="https://codepen.io/blythe4/pen/MLjwYw/" target="_blank">CodePen 예제</a>
    - 여백과 column의 넓이 둘다 가변적으로 화면 넓이의 비율에 따라 변한다.
    - 여백의 넓이는 항상 고정이고, column이 화면 넓이의 비율에 따라 변한다.

3. 레이아웃 넓이 고정
    > Break Point에 따라 각각 레이아웃의 넓이가 고정 또는 가변적으로 변경 <a href="https://codepen.io/blythe4/pen/yZGXeo" target="_blank">CodePen 예제</a>
    1. 가변적인 레이아웃 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cv.htm)
    2. 고정적인 레이아웃 + 가변적인 레이아웃 [예제](https://www.w3schools.com/w3css/tryw3css_templates_portfolio.htm)  

## 5. 이미지 요소  
> 디바이스에 따라 화면의 밀도가 2배에서 4배로 점점 증가하고 있다.  
> 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이상의 이미지가 필요하다.  

### 이미지를 어떻게 사용해야 할까?
1. 하나의 큰 이미지로 모든 디바이스 사용  
2. 디바이스별 이미지 사용
3. 밀도에 따른 이미지 사용
4. SVG 사용 : 로고, 아이콘([SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites))

### 이미지 표시 방법
1. 비율 따른 이미지 축소 및 확대 [LG화학 디지털아카이브 - 기네스북](http://developers.xeogen.com/blythe/lgarchive/guinness.html)
![이미지](/img/image-01-01.jpg)  
2. 디바이스별로 이미지를 다르게 표현  
![이미지](/img/responsive-img.png)  
3. 높이를 고정으로 하고 이미지를 가운데로 정렬 [예제](https://www.w3schools.com/w3css/tryw3css_templates_cafe.htm)

## 6. 동영상
> 동영상이 Background에서 자동재생+loop일때 
1. 화면에 꽉차게 표시  
: 동영상을 가운데 정렬 [사이트 예제](http://sugentech.com/KOR/)

## 7. 폰트  
1. 모바일 - 시스템 폰트 / 웹 - 웹폰트 사용
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


## 8. 표 
> 모바일 디바이스에서 대응 방법  
* [모바일에서 리스트 형태로 보기1](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [모바일에서 리스트 형태로 보기2](https://codepen.io/AllThingsSmitty/pen/MyqmdM)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))
* [모바일에서 슬라이드로 변환](https://medium.com/@andrejsabrickis/responsive-tables-made-simple-4609804ce60b)

## 9. 리스트
* 리스트의 순서 및 정렬
> HTML 마크업시 리스트는 순서대로 나열되며 순차적으로 왼쪽부터 쌓이게 된다. 두개 이상의 column이 있다면 오른쪽부터 하나씩 아래로 붙게 된다. 

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

## 10. Description List
> 제목이 포함 된 리스트 <a href="https://codepen.io/blythe4/pen/WPgvKX" target="_blank">CodePen 예제</a>

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

## 11. 원페이지 반응형
* 화면에서 보여지는 내용이 화면보다 많을 경우 내용이 화면에서 다 안보이고 화면 밖으로 넘어가 스크롤이 생기거나 이미지 또는 내용이 겹쳐보이거나 짤려보일 수 있다.(비율에 맞춰 작게 보이거나 여백이 많아져 보일 수도 있다.)
* 해상도 높이는 사용자마다 브라우저의 환경설정이 다르기 때문에 화면에 넘치거나, 여백이 많이 생길 수 도 있다.


### 해상도
1. HD : 1280x720  
2. FullHD : 1920x1080  
3. QHD : 2560x1440  

[예제1 - 한국산업단지공단](https://card.kicox.or.kr/main/main.do)  
[예제2 - LG화학 디지털아카이브(생명과학)](http://developers.xeogen.com/blythe/lgarchive/bioproduct.html)