# Plugin

## 이미지  
> [SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites)

### 1. [iconizr](https://iconizr.com/)
* 아이콘의 사이즈(Width, Height)는 동일 해야 한다.
* 아이콘 Sprite는 아래로 나열 된다.
* 추가하기 전 아이콘의 이름이 수정이 되면 class name도 달라지게된다.
* icon의 사이즈 조절시 background-size:100% auto로 설정하면 됨.
* background-image가 data URL이 아닌 sprite로 할 경우 background-position으로 위치를 다시 지정해 줘야 하기때문에 data URL 방법이 좋다.
* SVG data URLs : background-image의 url속성에서 data:~~~ 로 불러온다. 

[MDN - Data URLs](https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/Data_URIs) /
[Caniuse - Data URLs](http://caniuse.com/datauri)
[Data URL를 사용하여 웹 사이트 속도 향상](https://blog.teamtreehouse.com/using-data-uris-speed-website)

```html
<li title="icon-chat">
    <div class="icon-box">
        <div class="icon icon-chat icon-chat-dims">
            <!-- icon-chat -->
        </div>
    </div>
    <h2>icon-chat</h2>
</li>
```
```css
.icon-chat,.icon-chat\:regular{background-image:url('data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22300%22%20viewBox%3D%220%20-20%20512%20512%22%3E%3Cpath%20d%3D%22M256%200C120.55%200%200%2092.375%200%20217.988c0%2045.88%2016.29%2089.32%2047.234%20126.29L20.641%20446.96c-3.946%2015.226%2010.523%2028.934%2025.566%2024.023l135.672-44.28c23.969%206.155%2048.871%209.273%2074.121%209.273%20135.535%200%20256-92.465%20256-217.989C512%2091.391%20390.242%200%20256%200zm0%20395.977c-23.703%200-47.02-3.16-69.293-9.387a20.04%2020.04%200%200%200-11.594.246L68.52%20421.629l20.093-77.578a19.997%2019.997%200%200%200-4.66-18.57C55.2%20294.304%2040%20257.132%2040%20217.987c0-98.144%2096.898-177.992%20216-177.992s216%2079.848%20216%20177.992-96.898%20177.989-216%20177.989zm25-177.993c0%2013.809-11.191%2025-25%2025s-25-11.191-25-25c0-13.804%2011.191-25%2025-25s25%2011.196%2025%2025zm100%200c0%2013.809-11.191%2025-25%2025s-25-11.191-25-25c0-13.804%2011.191-25%2025-25s25%2011.196%2025%2025zm-200%200c0%2013.809-11.191%2025-25%2025s-25-11.191-25-25c0-13.804%2011.191-25%2025-25s25%2011.196%2025%2025zm0%200%22%2F%3E%3C%2Fsvg%3E');background-repeat:no-repeat}
.icon-chat-dims{width:300px;height:300px}
```

### [IE 브라우저](https://caniuse.com/#search=data)  
- IE8 : 최대 URL길이는 32KB, Non-base64-encoded SVG data URIs need to be uriencoded to work in IE and Firefox as according to the specification.    
- IE9 이상 : 최대 크기 제한은 4GB  

[Github HTML Preview](https://htmlpreview.github.io/)  
예제) https://github.com/blythe4/vscode-git/blob/master/responsive/Guide/iconizr/iconizr-preview.html

![이미지](/img/icon_01.png)  

### 2. [spritebot](https://github.com/thomasjbradley/spritebot#download)
* 로컬 파일에서 svg 표시 안나옴 loclahost로 확인. (https://learn-the-web.algonquindesign.ca/courses/web-dev-3/using-svg-icons/)  
* IE에선 external resouuce 동작 안됨.

## SVG 아이콘 폰트
* SVG 아이콘을 폰트처럼 사용  
* 폰트로 사용하기 때문에 단색만 사용가능  

### 1. [IcoMoon - Free](https://icomoon.io/app/#/select)
> [사용법](https://dkdlfhd.blog.me/220912398067)
* Import Icons > 불러온 파일에 오른쪽 끝 버튼을 눌러 Select All 클릭 > Generate font(setting으로 폰트 이름, Prefix 설정)
* Zip 압축을 풀고 안에 있는 css와 font 사용

    사용 예)  
    [HTML]
    ```html
    <span class="icon-newspaper"></span>
    <span class="icon-spades"></span>
    <span class="icon-file-video"></span>
    ```
    [CSS]
    ```css
    @font-face {
        font-family: 'icomoon';
        src:  url('fonts/icomoon.eot?xzoh1v');
        src:  url('fonts/icomoon.eot?xzoh1v#iefix') format('embedded-opentype'),
            url('fonts/icomoon.ttf?xzoh1v') format('truetype'),
            url('fonts/icomoon.woff?xzoh1v') format('woff'),
            url('fonts/icomoon.svg?xzoh1v#icomoon') format('svg');
        font-weight: normal;
        font-style: normal;
    }

    [class^="icon-"], [class*=" icon-"] {
        /* use !important to prevent issues with browser extensions that change fonts */
        font-family: 'icomoon' !important;
        speak: none;
        font-style: normal;
        font-weight: normal;
        font-variant: normal;
        text-transform: none;
        line-height: 1;

        /* Better Font Rendering =========== */
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }

    .icon-newspaper:before {
        content: "\e904";
    }
    .icon-spades:before {
        content: "\e917";
    }
    .icon-file-video:before {
        content: "\e92a";
    }
    ```

## 표  
* [모바일에서 리스트 형태로 보기1](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [모바일에서 리스트 형태로 보기2](https://codepen.io/AllThingsSmitty/pen/MyqmdM)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))