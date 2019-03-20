# Publisher

## Header

```html
[Meta Tag]
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

```html
기준(화면 넓이, 접속 디바이스 등..)을 정하고 해당 레이아웃이 변경되는 css만 불러오는 방법
<link rel="stylesheet" type="text/css" href="/web.css" media="screen and (min-width:1280px)" />
<link rel="stylesheet" type="text/css" href="/tablet.css" media="screen and (min-width:712px) and (max-width:1279px)" />
<link rel="stylesheet" type="text/css" href="/mobile.css" media="screen and (max-width:711px)" />
```

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
2. 이미지(비율, 높이고정, 밀도에 따른 배수 이미지)
3. 폰트 크기(디바이스 넓이에 맞춰 유동적인 사이즈, 고정사이즈)
4. 레이아웃 고정 넓이(Left menu)
5. column, gutter 넓이(비율, 고정)

## 이미지 파일명
* @Sufix로 구분한다.(w - PC / t - Tablet / m - Mobile)
* 만약 동일한 사이즈의 이미지를 사용한다면 디바이스의 넓이가 작은것으로 사용한다.  
    ex) Web과 Tablet의 사이즈가 같으면 Tablet 이미지 사용
<pre>
- img01@w.jpg
- img01@t.jpg
- img01@m.jpg

- img02@t.jpg
- img02@m.jpg
</pre>

## media query 사용한 css, 디바이스에 맞는 css
* 하나의 css로 반응형을 제작
    * 모듈화 시켜 반응형 만들기
    [html]
    ``` html
     <main class="l-wrap">
      <!-- Header [s] -->
      <header class="l-header">
          <h1>logo</h1>
      </header>
      <!-- Header [e] -->
      
      <!-- Container [s] -->
      <section class="l-container">
          <strong class="page-title">Page Title</strong>
          <p class="page-text">Page Text</p>
      </section>
      <!-- Container [s] -->
      
      <!-- Footer [s] -->
      <footer class="l-footer">
      </footer>
      <!-- Footer [e] -->
  </main>
  ```
  [CSS] - 모바일 우선 작업 시
  ``` css
    /* layout */
    .l-wrap{...}
    .l-header{...}
    .l-footer{...}  
    
    /* Mobile */
    @media screen and (max-width:711px){
        .l-header{...}
        .l-footer{...}
    }
    /* Tablet */
    @media screen and (min-width:712px){
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
    @media screen and (max-width:711px){
        .page-title{...}
        .page-text{...}
    }
    /* Tablet */
    @media screen and (min-width:712px){
        .page-title{...}
        .page-text{...}
    }
    /* web */
    @media screen and (min-width:1280px){
        .page-title{...}
        .page-text{...}
    }
  ```

    [CSS] - 웹 우선 작업 시
    ``` css
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
    ```

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

## 표 
* [모바일에서 리스트 형태로 보기1](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [모바일에서 리스트 형태로 보기2](https://codepen.io/AllThingsSmitty/pen/MyqmdM)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))
* [모바일에서 슬라이드로 변환](https://medium.com/@andrejsabrickis/responsive-tables-made-simple-4609804ce60b)