# 반응형 제작 시 유의사항  
> 우리들에게 필요한 반응형 웹 제작 시 유의사항은 무엇이 있을까? 다음 리스트에서 함께 확인해보자.  

## 1. 레이아웃  
> * 순차적인 순서가 아닌 디바이스(모바일, 테블릿, 웹)에서 각자 다른 위치 또는 순서를 나타낼 때  
> * 각 디바이스별 구조가 달라질때

![이미지](/img/history-m-01.jpg) 
![이미지](/img/history-m-02.jpg)  
![이미지](/img/history-t-01.jpg)  
![이미지](/img/history-w-01.jpg)  

## 2. Break Point(분기점, 중단점)
> 최소 사이즈를 기준으로 디바이스(web, tablet, mobile)에 따라 분기점이 필요합니다.  
<pre>
1. Mobile : 320px
2. Tablet : 720px
3. Web : 1280px
</pre>

<pre>
CSS 문법
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

![이미지](/img/responsive-breakpoint01.png)  
![이미지](/img/responsive-breakpoint02.png)  
[출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  
![이미지](/img/responsive-breakpoint03.jpg)  
[출처](http://brand-maestro.com/place-powerful-breakpoints-responsive-web-design/)

## 3. 모바일 기준 기획, 디자인
> 모바일부터 기준을 잡고 진행해야 할까 ?  
> 가장 작은 뷰에서부터 시작하자.  
> 필수 요소와 보조 요소를 분리하는데 도움이 되고, 내용을 우선으로 

![이미지](/img/design-mobile-first.png)  
[출처](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b)  


## 4. 이미지 요소  
> * 디바이스에따라 화면의 밀도가 2배에서 4배로 점점 높아지고 있다. 사용자가 화면을 봤을때 이미지가 흐려보이거나 깨져 보이지 않으려면 최소 2배 이미지가 필요하다.  
> * SVG를 sprite image로 사용 가능 여부와 Logo의 경우 SVG로 따로 사용하는 것을 고려해보자.
> * 이미지 표시
>   * 비율 따른 이미지 축소 및 확대
>   * 이미지가 디바이스별로 다를때
>   * 높이 고정인가?
> * 웹사이트 최적화를 위해서 각 디바이스별로 이미지를 따로 불러올것인지, 기준이되는 것을 정하는 것이 좋겠다.  

[SVG Sprite 방법](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites)

## 5. 텍스트 및 폰트  
> * 반응형이지만 모바일에서 시스템 폰트 사용 / 웹에서 웹폰트 사용  
> * 모바일 디바이스 넓이에 따라 폰트 크기는 고정 ?  
> * 텍스트의 줄바꿈 이슈  

* Web (왼쪽 - 줄바꿈 안함, 오른쪽 - 줄바꿈 적용)  
![이미지](/img/text.jpg) 
* Tablet (상단 - 줄바꿈 안함, 하단 - 줄바꿈 적용)    
![이미지](/img/text-nowrap.jpg)  
> CSS로 Tablet 기준으로 텍스트 줄바꿈 적용

## 6. 원페이지 반응형
> 노트북, 가로모드 처럼 16:9가 아닌 4:3 비율인 모니터나 디바이스들에서 한 화면에 보여지는 내용의 양이 많을 경우 내용이 짤리거나 생각되야 할 때가 생기는데 이때 해결 방법은 ? 모바일에서 내용이 보여지는 방식과 테블릿, pc에서 보여지는 내용이 달라져 보일 수 도 있다.

---
### 1. 사이트 접속 시 해당 디바이스 또는 화면의 넓이에 맞춰 css 다르게?  
* 하나의 css로 반응형을 제작하는방법
    * 모듈화 시켜 반응형 만들기

* 기준을 정하고 해당 레이아웃이 변경되는 css만 불러오는 방법
    <pre>
    - pc.css
    - tablet.css
    - mobile.css
    </pre>