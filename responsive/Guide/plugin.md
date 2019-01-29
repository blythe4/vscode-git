# Plugin

## 이미지  
> [SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites)

### 1. [iconizr](https://iconizr.com/)
* background-image 사용으로 사이즈 변경시 background-position 이슈 있음

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
    <code>&lt;span class="icon-home"&gt;&lt;/span&gt;</code>  
    [CSS]
    <code>.icon-home:before {content: "\e900";}</code>
    </pre>

## 표 
* [모바일에서 리스트 형태로 보기](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  