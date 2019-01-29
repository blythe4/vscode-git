# Designer


## 1. Break Point(분기점, 중단점)
* 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 분기점을 정한다.  
<pre>
1. Mobile : 320px
2. Tablet : 712px
3. Web : 1280px
</pre>

![이미지](/img/responsive-breakpoint01.png)  
[이미지 출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  


## 2. 모바일 기준 기획, 디자인  
* 가장 작은 뷰에서부터 시작하자.  
* Mobile 구성에서 요소들을 추가하여 Tablet, Web 레이아웃을 생각한다.

![이미지](/img/design-mobile-first.png)  
[이미지 출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  

## 3. 레이아웃  
1. 순차적인 순서가 아닌 디바이스(모바일, 테블릿, 웹)에서 각자 다른 위치를 나타낼 때  
: 각 디바이스별 구조가 달라질때 [LG화학 디지털아카이브 - 해외사업 히스토리](http://developers.xeogen.com/blythe/lgarchive/overseas.html)  
![이미지](/img/layout.jpg)  

## 4. 이미지 요소  
> 디바이스에따라 화면의 밀도가 2배에서 4배로 점점 높아지고 있다. 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이미지가 필요하다.  

1. 하나의 큰 이미지로 모든 디바이스 사용
2. 디바이스별 이미지 사용
3. 밀도에 따른 이미지 사용
4. SVG 사용 : 로고, 아이콘([SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites))


### 이미지 표시 방법
* 비율 따른 이미지 축소 및 확대 [LG화학 디지털아카이브 - 기네스북](http://developers.xeogen.com/blythe/lgarchive/guinness.html)
![이미지](/img/image-01.jpg) 
* 이미지가 디바이스별로 다를때 [LG화학 디지털아카이브 - 생명과학](http://developers.xeogen.com/blythe/lgarchive/bioproduct.html)
![이미지](/img/image-02.jpg) 


## 5. 폰트  
1. 모바일 - 시스템 폰트 / 웹 - 웹폰트 사용
2. 디바이스 넓이에 따라 폰트 크기 고정
    <pre>
    1. Web : 32px
    2. Tablet : 28px
    3. Mobile : 20px
    </pre>
3. 분기점 기준으로 디바이스 넓이에 따라 비율(vw 단위)로 사용  
![이미지](/img/rwd-font.png)   
    [vw단위 사용](https://www.aristidebenoist.com/)
    <pre>
    1. Web : 32px
    2. Tablet : 28px
    3. Mobile : 5.55vw
    </pre>

## 6. 텍스트
1. CSS로 Tablet 기준으로 텍스트 줄바꿈 적용
* Web (왼쪽 - 줄바꿈 안함, 오른쪽 - 줄바꿈 적용)  
![이미지](/img/text.jpg) 
* Tablet (왼쪽 - 줄바꿈 안함, 왼쪽 - 줄바꿈 적용)    
![이미지](/img/text-nowrap.jpg)  