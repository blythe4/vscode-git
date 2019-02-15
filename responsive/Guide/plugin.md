# Plugin

## 이미지  
> [SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites)

### 1. [iconizr](https://iconizr.com/)
* 추가되는 SVG 아이콘 이름, 사이즈 동일 해야 함  
* sprite는 아래로 추가 된다.
* icon의 사이즈 조절시 background-size:100% auto로 설정하면 됨.
* sprite에서 총 4개의 방법으로 아이콘을 보여주는데 SVG data URLs 방법으로 하면 잘됨!
* background-image의 url속성에서 data:~~~ 로 불러온다.

예제) /giude/iconizr/icons/iconizr-svg-data-preview.html

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
    <pre>
    사용 예)  
    [HTML]
    ```html
    <span class="icon-home"></span>
    ```
    [CSS]
    ```css
    .icon-home:before {content: "\e900";}
    ```
    </pre>

## 표  
* [모바일에서 리스트 형태로 보기](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  