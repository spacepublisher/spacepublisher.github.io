---
layout: post
title:  "시시콜콜 Z-INDEX 이야기"
date:   2018-05-12 00:00:00 +0900
categories: jekyll update
---
여러분들께서는 'z-index' 속성 많이 써보셨는지요.  
아마 홈페이지 하나 만들때, 이 속성이 한번도 안쓰이는 경우는 없을것 같습니다.  
보통 팝업같은것 만들때 많이 쓰이고, 그 외에도 많이 쓰입니다. 무척 대중적인 속성입니다.  
아무튼 퍼블리셔 입장에서 이것이 필요한 상황은 '특정 엘리먼트가 뒤쪽으로 파묻힌 상태이지만, 앞쪽으로 빼내어야 하는 경우'겠죠.

코드로 보면 이렇습니다.  
빨간박스가 뒤쪽에 파묻혀 있습니다. 이걸 앞쪽으로 꺼내고 싶은 거죠.

<p data-height="332" data-theme-id="0" data-slug-hash="LmrRvW" data-default-tab="css,result" data-user="verysomenice" data-embed-version="2" data-pen-title="z-index(1)" class="codepen">See the Pen <a href="https://codepen.io/verysomenice/pen/LmrRvW/">z-index(1)</a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

이럴땐 저는 이렇게 보통 합니다.  
빨간박스, 파란박스 모두 z-index를 주되, 빨간박스에 좀 더 큰 값을 정의합니다. 여기서는 빨간박스에는 10을, 파란박스에는 5를 정의했습니다.

<p data-height="265" data-theme-id="0" data-slug-hash="RyJGOx" data-default-tab="css,result" data-user="verysomenice" data-embed-version="2" data-pen-title="z-index(2)" class="codepen">See the Pen <a href="https://codepen.io/verysomenice/pen/RyJGOx/">z-index(2)</a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

## 자식에게 z-index를 부여해야 할 때
이번에는 조금 더 복잡한 케이스입니다.  
파란박스의 자식으로 하늘색동그라미가 있다고 칩시다.  
그리고, 하늘색동그라미를 빨간박스보다 더 돌출시키고 싶습니다.  
그래서 하늘색동그라미의 z-index 속 '9999'라는 무지막지한 수치를 정의해봤습니다.  
하지만 꿈쩍도 하지않습니다. 하늘색동그라미의 부모인 파란박스가 그 형제인 빨간박스보다 z-index가 이미 작기 때문입니다.  
즉 z-index는 '형제끼리의 싸움'이라고 결론내릴 수 있습니다.

<p data-height="265" data-theme-id="0" data-slug-hash="mLKrYx" data-default-tab="css,result" data-user="verysomenice" data-embed-version="2" data-pen-title="z-index(3)" class="codepen">See the Pen <a href="https://codepen.io/verysomenice/pen/mLKrYx/">z-index(3)</a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

그런데말입니다, 하늘색동그라미를 빨간박스보다 돌출시키는 방법은 정말 없는걸까요?  
즉, '하늘색동그라미 --> 빨간박스 --> 파란박스' 로 배치하는게 불가능한걸까요?  
2017년까지는 부끄럽게도, 저는 그게 불가능하다고 생각했습니다.  
문맥상 눈치채셨겠지만, '가능'합니다.  
방법은 파란네모의 z-index 값을 'auto'로 정의하는 것입니다.

<p data-height="265" data-theme-id="0" data-slug-hash="WJyGqm" data-default-tab="css,result" data-user="verysomenice" data-embed-version="2" data-pen-title="z-index(4)" class="codepen">See the Pen <a href="https://codepen.io/verysomenice/pen/WJyGqm/">z-index(4)</a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

## 결론
결론적으로, z-index는 무조건 형제끼리의 대결이 아닙니다.  
우선은 형제끼리 대결을 하는게 기본이지만,  
그 형제의 z-index 값이 auto이면, 대결의 대상을 자식에게 바톤터치를 한다고 볼 수 있겠습니다.

놀랍지 않으신지요...  
아님말구요, 저는 놀랬거든요.  
이것으로 포스팅을 마칩니다.
