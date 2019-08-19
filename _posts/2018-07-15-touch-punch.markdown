---
layout: post
title:  "Touch Punch"
date:   1988-07-15 00:00:00 +0900
categories: jekyll update
---
제가 이번에 새롭게 투입된 프로젝트는 디지털 교과서(이하, DT) 프로젝트입니다.   
특별히 복잡한 js 코드나, 러닝커브 높은 js 라이브러리는 없었습니다. 다행이도요.   
특이점을 꼽자면 Touch Punch 정도.   
전부터 집에서 혼자 깨작깨작 가지고는 놀아봤지만,   
실제 프로젝트에서 만난것은 처음입니다.   
아마도, 디지털 교과서는 태블릿이 가장 중요한만큼,    
그러다보니, 터치 기반의 모션 스크립트가 꽤 들어가는 편이고,    
이에따라 필연적으로 Touch Punch는 모든 DT 제작자들의 1순위 라이브러리일것입니다.

## Touch Punch...?
Touch Punch라는 녀석이 있습니다.    
Touch Punch는 jQuery UI의 '서포터'에 불과합니다. 따라서, jQuery UI라는 녀석을을 먼저 알아야 합니다.

## 그전에, jQuery UI
jQuery UI는 보통 많이 쓰는 기본 jQuery 라이브러리에 종속되는 라이브러리입니다.   
구체적으로 많이 쓰이는 UI를 미리 구현해놓은겁니다.   
퍼블리셔라면 한번쯤은 코딩해 보았을 유명한것들이 있죠.   
탭메뉴 라던가, 아코디온같은 것들이요.   
다음 링크들을 참고하시면 해당 UI를 금방 뚝딱 구현할 수 있습니다.

- [https://jqueryui.com/tabs/][link1]
- [https://jqueryui.com/accordion/][link2]

[link1]: https://jqueryui.com/tabs/
[link2]: https://jqueryui.com/accordion/

## jQuery UI - Interactions
하지만 뭐니뭐니해도 jQuery UI의 꽃은 Interactions라고 생각합니다.   
이게 뭐냐면, 특정 요소를 마우스다운 상태로 이리저리 끌고 다니다가 마우스업 시 그 자리에 고정되는 UI같은것들이요.   
차라리 아코디온이나 탭메뉴는 직접 금방 만들 수 있습니다.   
그런데 이런 인터랙션을 직접 구현하려면 아마 머리좀 아파지죠   
이런것들은 미리 jQuery UI에서 구현해 놓은것입니다. 정말 대단하죠.   
다음은 제가 간단하게 만든 데모입니다. 빨간 네모를 마우스로 끌고다녀보세요. 그리고, 크롬개발자도구로 모바일모드로 바꿔서 터치이벤트로 해보세요. 작동 안할겁니다.   

<div class="codepen" data-default-tab="js,result" data-embed-version="2" data-height="265" data-pen-title="Hello jQuery UI " data-slug-hash="PaMzjW" data-theme-id="0" data-user="verysomenice">
See the Pen <a href="https://codepen.io/verysomenice/pen/PaMzjW/">Hello jQuery UI </a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io/">CodePen</a>.</div>
<script async="" src="https://static.codepen.io/assets/embed/ei.js"></script>

## 다시, Touch Punch
그러나, 이 훌륭한 Interactions 기능들은, 마우스 기반에서만 동작합니다.   
즉, 스마트폰이나 태블릿으로는 동작하지 않는다는겁니다. 정말 아쉽죠.   
하지만, 이 안되는걸 가능하게 바꿔주는 라이브러리가 바로 Touch Punch입니다. 정말 대단하죠.   
뭐 별도 펑션 호출같은 작업도 없습니다. 그저 jQuery Ui 다음에 스크립트 추가를 해두면 알아서 됩니다.   
제가 만든 데모입니다. 이번에도 크롬개발자도구로 모바일모드로 바꿔서 터치이벤트로 해보세요. 이번엔 작동 할겁니다.

<div class="codepen" data-default-tab="js,result" data-embed-version="2" data-height="265" data-pen-title="Hello Touch Punch" data-slug-hash="KeOWOp" data-theme-id="0" data-user="verysomenice">
See the Pen <a href="https://codepen.io/verysomenice/pen/KeOWOp/">Hello Touch Punch</a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io/">CodePen</a>.</div>
<script async="" src="https://static.codepen.io/assets/embed/ei.js"></script>
