# 반응형 제작

## 1. Break Point(분기점, 중단점)
* 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 Break Point를 정한다.  
<pre>
1. Mobile : 320px
2. Tablet : 712px
3. Web : 1280px
</pre>

### Break Point 별 표시 내용
    - 레이아웃 고정 넓이(Left menu)
    - 여백 넓이(고정, 넓이 비율)
    - column, gutter 넓이(비율, 고정)
    - 이미지(비율, 높이고정, 밀도에 따른 배수 이미지)
    - 동영상(비율, 화면 Full)
    - 폰트 크기(디바이스 넓이에 맞춰 유동적인 사이즈, 고정사이즈)
    - GNB 메뉴 표시

## 2. 모바일 기준 기획, 디자인  
* 가장 작은 뷰에서부터 시작하자.  
* Mobile 구성에서 요소들을 추가하여 Tablet, Web 레이아웃을 생각한다.

## 3. 폴더 및 파일명
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
1. 순차적인 순서가 아닌 디바이스(모바일, 테블릿, 웹)에서 각자 다른 위치를 나타낼 때  
: 각 디바이스별 구조가 달라질때
2. 여백 
    > <a href="https://codepen.io/blythe4/pen/MLjwYw/" target="_blank">CodePen 예제</a>
    - 여백과 column의 넓이 둘다 유동적으로 화면의 넓이에 따라 변한다.
    - 여백의 넓이는 항상 고정이고, column이 화면의 넓이의 비율에 따라 변한다.

3. 레이아웃 넓이 고정
    > Break Point에 따라 각각 레이아웃의 넓이가 고정 또는 유동적으로 변경
    1. 유동적인 레이아웃
    2. 고정적인 레이아웃 + 유동적인 레이아웃

## 5. 이미지 요소  
> 디바이스에따라 화면의 밀도가 2배에서 4배로 점점 증가하고 있다.  
> 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이상의 이미지가 필요하다.  

### 이미지를 어떻게 사용해야 할까?
1. 하나의 큰 이미지로 모든 디바이스 사용  
2. 디바이스별 이미지 사용
3. 밀도에 따른 이미지 사용
4. SVG 사용 : 로고, 아이콘([SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites))

### 이미지 표시 방법
1. 비율 따른 이미지 축소 및 확대
2. 디바이스별로 이미지를 다르게 표현

## 6. 동영상
> 동영상이 Background에서 자동재생+loop일때 
1. 화면에 꽉차게 표시  
: 동영상을 가운데 정렬 [사이트 예제](http://sugentech.com/KOR/)
2. Break Point에 따라서 비율에 맞춰 표시

## 7. 폰트  
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

## 8. 표 
* 모바일 디바이스에서 대응 방법  
* [모바일에서 리스트 형태로 보기](https://www.jqueryscript.net/demo/Small-Responsive-Table-Plugin-with-jQuery-CSS3-Stacked-Rows/)
* [테이블 column Select box로 선택해서 보기](http://gergeo.se/RWD-Table-Patterns/)  
* 테이블 고정([상단고정](https://codepen.io/blythe4/pen/qgaBVG/), [좌측고정](https://codepen.io/blythe4/pen/OdRJvb/))

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
> 제목이 포함 된 리스트  
<a href="https://codepen.io/blythe4/pen/WPgvKX" target="_blank">CodePen 예제</a>

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
