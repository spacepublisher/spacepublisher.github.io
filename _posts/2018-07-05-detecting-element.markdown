---
layout: post
title:  "특정 엘리먼트의 크기 변화를 감지하는 방법"
date:   2018-07-15 00:00:00 +0900
categories: jekyll update
---
특정 엘리먼트의 너비값이 변경되면, 이를 감지해야할 필요할때가 있을겁니다. 안타깝게도 기본적인 제이쿼리 API인 resize()는 오로지 브라우저 자체의 사이즈 변화만 감지합니다. 이때 필요한 제이쿼리 플러그인 하나를 소개합니다.

## 여기서 다운로드 받으세요
[https://github.com/sdecima/javascript-detect-element-resize][link1]

[link1]: https://github.com/sdecima/javascript-detect-element-resize

## 사용법
{% highlight javascript %}
$('특정엘리먼트의 클래스나 아이디').resize(function() {  
 //...  
});  
{% endhighlight %}

## 심화
플러그인은 그저 잘 호출해서 잘 써먹으면 그만입니다...만.  
저는 평소와는 다르게, 좀 궁금했습니다.  
그야말로 '불가능한것을 가능하게'했으니까요. 분명 각 개별 특정 엘리먼트들은 박스모델의 크기변화를 감지하는 스팩이 없습니다.  
[(현재 그것을 하게 해달라고 요청중이긴 합니다.)][link2]
[link2]: https://drafts.csswg.org/resize-observer-1/

## setInterval
당장에 떠오르는것은 setInterval이었습니다.  
그러나, 딱히 성능 측정을 하지 않더라도, 이 최악의 방법을 쓰느니 차라리 기획자를 설득하여 기능을 없애는게 낫다라고 생각하는 것은 저뿐만이 아닐겁니다.  
이 플러그인 개발자 역시 설마 이걸 쓰진 않았을거라 생각했지만... setInterval이 아니라면 도저히 모르겠더군요.

## requestAnimationFrame
그래서 왜, 굳이, 또 코드를 분석해보니, [requestAnimationFrame][link3](이하, RAF)가 핵심이었습니다. RAF는 브라우저가 새롭게 그림을 그려야하는 '상황'을 감지합니다.
즉, 특정 엘리먼트의 크기가 줄거나 늘어나면 그것이 바로 새롭게 그림을 그려야 하는 상황일것입니다.
결론적으로 RAF가 핵심이고, RAF는 setInterval과 사용법이 유사해서, 코드를 금방 짤 수 있습니다.
다만, RAF는 여전히 IE9이하에서는 안되는 스팩입니다. 이런 부분 처리 및 혹시모를 버그등을 생각하면 당장은 위에서 추천드린 플러그인을 이용하시길 바랍니다.

[link3]: https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame

## 여담, jquery 진영
jquery 버전3대는 [animate()를 setInterval에서 RAF로 바꾸는 작업][link4]을 했습니다. 속도 측면에서 확실히 좋긴 좋나 봅니다. 결론적으로는 모든것을 다 RAF로 바꾸진 못했다고 합니다. jquery가 꽤 범용성이다 보니, 다양한 상황을 대응하는게 여간 어려운게 아닐겁니다.

[link4]: https://blog.jquery.com/2016/06/09/jquery-3-0-final-released/

읽기 귀찮은 분들을 위해, 저퀄리티 번역을 덫붙이고 끝내겠습니다.

> IE9이하, 안드4.4이하를 제외한 모든 플랫폼에서는 raf를 지원합니다. raf는 CPU타임을 감소하고 애니메이션도 더 부드럽습니다. 이러한 전차로 모바일에서는 배터리 절약효과가 있습니다.  

> On platforms that support the requestAnimationFrame API, which is pretty much everywhere but IE9 and Android<4.4, jQuery will now use that API when performing animations. This should result in animations that are smoother and use less CPU time – and save battery as well on mobile devices.

> jquery는 과거에도 raf를 적용해보려고 했던적이 있습니다. 그러나 기존 코드와 심각한 호환성 이슈가 발생했고, 다시 되돌려놔야만 했습니다.

> jQuery tried using requestAnimationFrame a few years back but there were serious compatibility issues with existing code so we had to back it out.

> 우리의 생각에, 우리는 그 이슈들을 다 뽀갰습니다. 브라우저 탭이 눈에서 보이지 않을땐 애니메이션을 중단시키는 식으로 말이죠. 그러나 여전히, 많은 코드들이 [거의 실시간]으로 돌아가는 애니메이션에 (setInterval을 의미하는듯) 기대어 만들어져있습니다. [거의 실시간]은 비현실적인 가정임을 우리도 알지만서도 지금은 어쩔수없이 코드가 그리 되어있는 상태입니다.

> We think we’ve beaten most of those issues by suspending animations while a browser tab is out of view. Still, any code that depends on animations to always run in nearly real-time is making an unrealistic assumption.
