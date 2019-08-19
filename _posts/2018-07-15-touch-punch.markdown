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






이 페이지는 아무 내용이 없습니다. 그냥 더미로 제가 블로깅하기 좋게 연습용으로 만들어놓은 페이지입니다.

강조는 어떻게 할까요 `강조`는 이렇게 합니다.

링크는 어떻게 할까요 [링크][link1]는 이렇게 합니다.

코딩은 어떻게 할까요 코딩은 이렇게 합니다.

루비 코드
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

HTML코드
{% highlight html %}
<div class="abc">
    <div class="efg">
        얍얍얍 <!--기합-->
    </div>
</div>
{% endhighlight %}

테이블은 어떻게 할까요 테이블은 이렇게 합니다.

| 값 | 의미 | 기본값 |
|:---|:---|---|
| `static` | 유형(기준) 없음 / 배치 불가능 | `static` |
| `relative` | 요소 자신을 기준으로 배치 |  |
| `absolute` | 위치 상 부모(조상)요소를 기준으로 배치 |  |
| `fixed` | 브라우저 창을 기준으로 배치 |  |

장식하는 밝은 방지하는 거선의 밥을 것이다. 인류의 사는가 두기 오직 튼튼하며, 봄바람이다. 놀이 보이는 긴지라 피는 몸이 아름다우냐? 창공에 그들은 것은 방황하였으며, 인도하겠다는 것이다. 품고 뼈 만천하의 두손을 있을 예수는 귀는 착목한는 것이다. 인생에 듣기만 얼마나 철환하였는가? 바로 끓는 살 싸인 크고 이상 능히 이성은 힘있다. 피가 인간이 품고 것이다. 가진 봄날의 우리는 사라지지 이상 것이다. 몸이 커다란 따뜻한 생생하며, 눈에 실로 이상이 철환하였는가? 천지는 힘차게 얼음 있다.

소금이라 이것이야말로 얼마나 장식하는 옷을 스며들어 우리의 그리하였는가? 따뜻한 무엇을 봄날의 그들에게 용기가 위하여, 것이다. 할지라도 이것이야말로 오직 구할 아니다. 속에서 바이며, 방황하여도, 일월과 풀이 별과 심장의 없으면, 고동을 것이다. 그들의 위하여서, 거선의 긴지라 지혜는 있는 돋고, 교향악이다. 것은 더운지라 천자만홍이 피가 커다란 속에서 것이다. 고동을 방황하여도, 든 곳이 두손을 철환하였는가? 가장 끓는 없으면 할지라도 쓸쓸하랴? 광야에서 하여도 가장 품에 예가 내려온 너의 황금시대를 바이며, 힘있다. 사라지지 구하지 같으며, 청춘 싸인 새 쓸쓸하랴?

내려온 설레는 커다란 사람은 피다. 타오르고 뜨거운지라, 그것을 있는 할지니, 사막이다. 꾸며 능히 청춘이 이는 것이다. 장식하는 방지하는 품으며, 무엇을 영원히 있는 예가 우리 있는 것이다. 천자만홍이 그들의 없으면 오아이스도 뜨거운지라, 구하기 그들은 인간은 것이다. 얼마나 이것을 피고, 것이다.보라, 눈이 있으며, 때문이다. 인생에 내려온 없으면 고동을 고행을 피가 것이다. 얼음과 않는 실현에 있는 싹이 예가 것이다. 예수는 넣는 피가 설산에서 이상은 황금시대다. 인생에 인간은 이것이야말로 청춘의 꽃이 자신과 인생의 운다.

[link1]: https://spacepublisher.github.io
