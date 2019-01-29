# Publisher

## Header
<pre>
    Meta Tag
    &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;

    : 기준(화면 넓이, 접속 디바이스 등..)을 정하고 해당 레이아웃이 변경되는 css만 불러오는 방법
    &lt;link rel="stylesheet" type="text/css" href="/web.css" media="screen and (min-width:1280px)" /&gt;
    &lt;link rel="stylesheet" type="text/css" href="/tablet.css" media="screen and (min-width:712px) and (max-width:1279px)" /&gt;
    &lt;link rel="stylesheet" type="text/css" href="/mobile.css" media="screen and (max-width:711px)" /&gt;
</pre>

## Break Point(분기점, 중단점)
* 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 분기점을 정한다.  
<pre>
1. Mobile : 320px
2. Tablet : 712px
3. Web : 1280px
</pre>

## Break Point에 따른 요소 정의
* 분기점을 기준으로 헤더 메뉴를 구분(media query)
* 사이트 접속 디바이스로 구분  
: PC, Laptop 접속(Web 표시) / Mobile, Tablet 접속(mobile, Tablet 표시)

1. 햄버거 메뉴 표시
2. 이미지
3. 폰트 크기
4. 레이아웃 고정 넓이(LNB, aside)

## media query 사용한 css, 디바이스에 맞는 css
* 하나의 css로 반응형을 제작
    * 모듈화 시켜 반응형 만들기
    <pre>
    [HTML]
    <code>
    &lt;main class="l-wrap"&gt;
        &lt;!-- Header [s] --&gt;
        &lt;header class="l-header"&gt;
            &lt;h1&gt;logo&lt;/h1&gt;
        &lt;/header&gt; 
        &lt;!-- Header [e] --&gt;
        
        &lt;!-- Container [s] --&gt;
        &lt;saction class="l-container"&gt;
            &lt;strong class="page-title"&gt;Page Title&lt;/strong&gt;
            &lt;p class="page-text"&gt;Page Text&lt;/p&gt;
        &lt;/section&gt;
        &lt;!-- Container [s] --&gt;
        
        &lt;!-- Footer [s] --&gt;
        &lt;footer class="l-footer"&gt;
        &lt;/footer&gt;    
        &lt;!-- Footer [e] --&gt;
    &lt;/main&gt;
    </code>
    </pre>
    
    <pre>
    [CSS] - 모바일 우선 작업 시
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

    <pre>
    [CSS] - 웹 우선 작업 시
    <code>
    /* layout */
    .l-wrap{...}
    .l-header{...}
    .l-footer{...}  
    /* web */
    @media screen and (min-width:1280px){
        .l-wrap{...}
        .l-header{...}
    }  
    /* Tablet */
    @media screen and (max-width:1279px){
        .l-wrap{...}
        .l-header{...}
        .l-footer{...}
    }
    /* Mobile */
    @media screen and (max-width:711px){
        .l-header{...}
        .l-footer{...}
    }
    /* common */
    .page-title{...}
    .page-text{...}    
    /* web */
    @media screen and (min-width:1280px){
        .page-title{...}
        .page-text{...}
    }   
    /* Tablet */
    @media screen and (max-width:1279px){
        .page-title{...}
        .page-text{...}
    }
    /* Mobile */
    @media screen and (max-width:711px){
        .page-title{...}
        .page-text{...}
    }
    </code>
    </pre>

## 폰트  
1. 모바일 - 시스템 폰트 / 웹 - 웹폰트 사용
2. 디바이스 넓이에 따라 폰트 크기 고정
    <pre>
    1. Web : 32px
    2. Tablet : 28px
    3. Mobile : 20px
    </pre>
3. 분기점 기준으로 디바이스 넓이에 따라 비율(vw 단위)로 사용
    <pre>
    1. Web : 32px
    2. Tablet : 28px
    3. Mobile : 5.55vw
    </pre>

## 텍스트
1. CSS로 Tablet 기준으로 텍스트 줄바꿈 적용
* Web (왼쪽 - 줄바꿈 안함, 오른쪽 - 줄바꿈 적용)  
![이미지](/img/text.jpg) 
* Tablet (왼쪽 - 줄바꿈 안함, 왼쪽 - 줄바꿈 적용)    
![이미지](/img/text-nowrap.jpg)  

## 표 
* 모바일 디바이스에서 대응 방법  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))
* [모바일에서 리스트 형태로 보기](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)  
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
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
