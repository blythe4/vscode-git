# 반응형 제작 시 유의사항  
> 우리들에게 필요한 반응형 웹 제작 시 유의사항은 무엇이 있을까? 다음 리스트에서 함께 확인해보자.  

## 1. Break Point(분기점, 중단점)
> 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 분기점을 정한다.  
<pre>
1. Mobile : 320px
2. Tablet : 720px
3. Web : 1024px
</pre>

![이미지](/img/responsive-breakpoint01.png)  
![이미지](/img/responsive-breakpoint02.png)  
[이미지 출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  
![이미지](/img/responsive-breakpoint03.jpg)  
[이미지 출처](http://brand-maestro.com/place-powerful-breakpoints-responsive-web-design/)

<pre>
<code>
 /* Mobile */

 /* Tablet */
 @media (min-width: 720px) and (max-width: 1279px) {

 }
 /* 가로 */
 @media only screen and (orientation: landscape) {

 }

 /* web */
 @media (min-width: 1280px) {

 }
</code>
</pre>

### 분기점 구분
> * 분기점을 기준으로 헤더 메뉴를 구분(media query)
> * 사이트 접속 디바이스로 구분  
> : PC, Laptop 접속(Web 표시) / Mobile, Tablet 접속(mobile, Tablet 표시)
    <pre>
    1. 햄버거 메뉴 표시
    2. 이미지
    3. 폰트 크기
    4. 레이아웃 고정 넓이(LNB, aside)
    </pre>


## 2. 모바일 기준 기획, 디자인  
> * 가장 작은 뷰에서부터 시작하자.  
> * 필수 요소와 보조 요소를 분리하는데 도움이 된다.
> * Mobile 구성에서 요소들을 추가하여 Tablet, Web 레이아웃을 생각한다.

![이미지](/img/design-mobile-first.png)  
[이미지 출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  

## 3. 레이아웃  
> 1. 순차적인 순서가 아닌 디바이스(모바일, 테블릿, 웹)에서 각자 다른 위치를 나타낼 때  
> 2. 각 디바이스별 구조가 달라질때 [LG화학 디지털아카이브 - 해외사업 히스토리](http://developers.xeogen.com/blythe/lgarchive/overseas.html)  
> ![이미지](/img/layout.jpg)  

## 4. 이미지 요소  
> 디바이스에따라 화면의 밀도가 2배에서 4배로 점점 높아지고 있다. 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이미지가 필요하다.  

1. SVG를 sprite image로 사용 가능 여부와 Logo의 경우 SVG로 따로 사용하는 것을 고려해보자.
    ([SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites))
2. 하나의 이미지로 모든 디바이스 사용
3. 각 디바이스별로 이미지를 따로 사용

### 이미지 표시 방법
> * 비율 따른 이미지 축소 및 확대 [LG화학 디지털아카이브 - 기네스북](http://developers.xeogen.com/blythe/lgarchive/guinness.html)
> ![이미지](/img/image-01.jpg) 
> * 이미지가 디바이스별로 다를때 [LG화학 디지털아카이브 - 생명과학](http://developers.xeogen.com/blythe/lgarchive/bioproduct.html)
> ![이미지](/img/image-02.jpg) 


## 5. 텍스트 및 폰트  
> 1. 모바일 - 시스템 폰트 / 웹 - 웹폰트 사용
> 2. 디바이스 넓이에 따라 폰트 크기 고정
    <pre>
    1. Web : 32px
    2. Tablet : 24px
    3. Mobile : 20px
    </pre>

## 6. 표 
> * 모바일 디바이스에서 대응 방법  
> * [모바일에서 리스트 형태로 보기](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)  
> * [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
    <pre>
    - 스크롤
    - column이나 row를 기준으로 테이블 새로 만들기
    - 테이블이 아닌 리스트 형태의 디자인
    </pre>
    1. [Scroll - Table]  
    ![이미지](/img/table-scroll.png)    
    2-1. [Web - Table]  
    ![이미지](/img/table-web.png)    
    2-2. [Mobile - Table]  
    ![이미지](/img/table-mobile.png)  
    3-1. [Web - Table]  
    ![이미지](/img/table-list-web.png)    
    3-2. [Mobile - Table]  
    ![이미지](/img/table-list-mobile.png)  

--------------------------

# 퍼블리싱

## Header
<pre>
    Meta Tag
    &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;

    : 분기점에 따른 CSS 반영    
    &lt;link rel="stylesheet" type="text/css" href="/web.css" media="screen and (min-width:1280px)" /&gt;
    &lt;link rel="stylesheet" type="text/css" href="/tablet.css" media="screen and (min-width:712px) and (max-width:1279px)" /&gt;
    &lt;link rel="stylesheet" type="text/css" href="/mobile.css" media="screen and (max-width:711px)" /&gt;
</pre>

## 1. media query 사용한 css, 디바이스에 맞는 css
* 하나의 css로 반응형을 제작
    * 모듈화 시켜 반응형 만들기
    <pre>
    <code>
    /* layout */
    .l-wrap{...}
    .l-header{...}
    .l-footer{...}  
    /* Mobile */
    @media screen and (max-width:959px){
        .l-header{...}
        .l-footer{...}
    }
    /* Tablet */
    @media screen and (min-width:960px){
        .l-wrap{...}
        .l-header{...}
        .l-footer{...}
    }
    /* web */
    @media screen and (min-width:1280px){
        .l-wrap{...}
        .l-header{...}
    }  

    /* common */
    .page-title{...}
    .page-text{...}    
    /* Mobile */
    @media screen and (max-width:959px){
        .page-title{...}
        .page-text{...}
    }
    /* Tablet */
    @media screen and (min-width:960px){
        .page-title{...}
        .page-text{...}
    }
    /* web */
    @media screen and (min-width:1280px){
        .page-title{...}
        .page-text{...}
    }   
    
    </code>
    </pre>

* 기준(화면 넓이, 접속 디바이스 등..)을 정하고 해당 레이아웃이 변경되는 css만 불러오는 방법
    <pre>
    &lt;link rel="stylesheet" type="text/css" href="/web.css" media="screen and (min-width:1280px)" /&gt;
    &lt;link rel="stylesheet" type="text/css" href="/tablet.css" media="screen and (min-width:712px) and (max-width:1279px)" /&gt;
    &lt;link rel="stylesheet" type="text/css" href="/mobile.css" media="screen and (max-width:711px)" /&gt;
    </pre>

## 2.이미지 사용
* 모바일에서 이미지 불러올 때 리소스 이슈
    1. 하나의 큰 이미지 사용
    2. 디바이스별 이미지 사용
    3. 밀도에 따른 이미지 사용
* SVG 사용 : 로고, 아이콘

## 3. 원페이지 반응형
> * 노트북, 디바이스 가로모드 처럼 16:9가 아닌 4:3 비율인 화면에서 보여지는 내용의 양(높이)이 많을 경우 내용이 화면에서 다 안보이고 화면 밖으로 넘어가 스크롤이 생기거나 이미지나 내용이 짤려질때(비율에 맞춰 작게 보이거나 여백이 많아져 보일 수도 있다.)
> * 모바일에서 내용이 보여지는 방식과 테블릿, pc에서 보여지는 내용이 달라져 보일 수 도 있다.


## 4. 텍스트
> CSS로 Tablet 기준으로 텍스트 줄바꿈 적용
> * Web (왼쪽 - 줄바꿈 안함, 오른쪽 - 줄바꿈 적용)  
> ![이미지](/img/text.jpg) 
> * Tablet (왼쪽 - 줄바꿈 안함, 왼쪽 - 줄바꿈 적용)    
> ![이미지](/img/text-nowrap.jpg)  