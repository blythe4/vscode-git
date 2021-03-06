# 반응형 제작

## 1. Break Point(분기점, 중단점)
* 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 Break Point를 정한다.  
<pre>
1. Mobile : 320px
2. Tablet : 712px
3. Web : 1280px
</pre>

![이미지](/img/responsive-breakpoint01.png)  
![이미지](/img/responsive-breakpoint02.png)  
[이미지 출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  
![이미지](/img/responsive-breakpoint03.jpg)  
[이미지 출처](http://brand-maestro.com/place-powerful-breakpoints-responsive-web-design/)

## 2. 모바일 기준 기획, 디자인  
* 가장 작은 뷰에서부터 시작하자.  
* Mobile 구성에서 요소들을 추가하여 Tablet, Web 레이아웃을 생각한다.

![이미지](/img/design-mobile-first.png)  
[이미지 출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  

## 3. 레이아웃  
1. 순차적인 순서가 아닌 디바이스(모바일, 테블릿, 웹)에서 각자 다른 위치를 나타낼 때  
: 각 디바이스별 구조가 달라질때
![이미지](/img/layout.jpg)  

## 4. 이미지 요소  
> 디바이스에따라 화면의 밀도가 2배에서 4배로 점점 증가하고 있다.  
> 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이상의 이미지가 필요하다.  

### 이미지 어떻게 사용해야 할까?
1. 하나의 큰 이미지로 모든 디바이스 사용  
2. 디바이스별 이미지 사용
3. 밀도에 따른 이미지 사용
4. SVG 사용 : 로고, 아이콘([SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites))

### 이미지 표시 방법
* 비율 따른 이미지 축소 및 확대
* 이미지가 디바이스별로 다를때

## 5. 폰트  
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

## 6. 표 
* 모바일 디바이스에서 대응 방법  
* [모바일에서 리스트 형태로 보기](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))

## 7. 폴더 및 파일명
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

## 8. 리스트
* 리스트의 순서 및 정렬

 <a href="https://codepen.io/blythe4/pen/NoBWgo" target="_blank">CodePen 예제</a>

<pre>
01. List  02.List  
03. List  04.List  
05. List  06.List  
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

<pre>
01. List  04.List  
02. List  05.List  
03. List  06.List  
</pre>

```html
<ul>
    <li>01. List</li>
    <li>02. List</li>
    <li>03. List</li>
</ul>
<ul>
    <li>04. List</li>
    <li>05. List</li>
    <li>06. List</li>
</ul>
```