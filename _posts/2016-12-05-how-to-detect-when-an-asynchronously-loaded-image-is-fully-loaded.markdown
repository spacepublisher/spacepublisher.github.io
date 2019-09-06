---
layout: post
title:  "비동기적으로 로드한 이미지가 완전히 로드된 시점을 감지하는 방법"
date:   2016-12-05 00:00:00 +0900
categories: jekyll update
---
## 개요
페이지 최초 로드시 이미지의 개수나 용량이 크다면 사용자 입장에서는 부담스러울 수가 있습니다. 그럴때는 보통 비동기 방식으로 사용자가 원할때 로드하는 방식을 씁니다. 이때 단순하게 이미지를 SHOW/HIDE 하는것을 넘어서서 자바스크립트를 활용하여 엘리먼트의 배치나 스타일을 조작해야 할 때가 있습니다. 이러한 스타일 조작이 이미지의 너비, 높이에 종속적이라면, 반드시 이미지가 '완전히' 로드될때까지 '기다려야'합니다. 이 '기다리는' 방법은 [스택오버플로우의 Aureliano Far Suau님의 답변 코드][link1]를 통해 해결했습니다.

[link1][http://stackoverflow.com/a/24512163/6948053]

## 원리
{% highlight javascript %}
var loaded = 0;
$('img').on('load', function() {
   loaded++;
   if(loaded == $('img').length){
      // do something
   }
});
{% endhighlight %}

원리는 간단합니다. 글로벌 변수 loaded에 선언 및 0 정의를 합니다. 원하는 이미지에 'load'이벤트를 겁니다. 한개의 이미지가 로드될때마다 loaded변수를 1씩 더해줍니다. '지금 로드받은 이미지가 마지막인가?'를 계속 물어봅니다. '마지막이 맞아'일때 if문 안쪽의 코드가 작동하게됩니다. 즉, 모든 이미지가 다운받아진 그 순간에 작동하게 됩니다.

## 응용 코드
[swiper.js를 활용하여 섬네일 클릭시 팝업을 띄우는 캐러셀][link2]을 만들어 보았습니다.

[link2][https://plnkr.co/edit/TeSoOyvqWKPRLq8Y0c81]
