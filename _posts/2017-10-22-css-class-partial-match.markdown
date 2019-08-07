---
layout: post
title:  "CSS 클래스 부분 일치"
date:   2017-10-22 00:00:00 +0900
categories: jekyll update
---

#배경
회사 프로젝트의 CSS파일을 보다보니, 다음과같은 문법이 눈에 띄었습니다.
{% highlight css %}
[class^="icon-"]:hover, [class*=" icon-"]:hover {
 opacity: 0.5;
}
{% endhighlight %}
당황스러웠지만 당황하지 않고 구글링 해보았습니다.

#문법정리
블라블라로 '시작'할때 (begin)
블라블라로 '끝'날때 (end)
어디든 블라블라가 낑겨있을때 (elsewhere)

#개인적 생각
코드 레벨에서 보자면 뚜렷하게 장점이 있는 문법입니다.
프로젝트 레벨에서 보자면 딱히 쓰고싶지 않은 문법입니다.

#효용성
이런 편리함이 생깁니다.
btn이 있고, btn-01, btn-02 두가지 디자인 가이드가 있다고 칩시다.
총 3가지 방식의 코드를 보여드리겠습니다. '방식3'에서 진면모가 드러납니다.

#크로스브라우징
IE11부터 사용가능, iOS10부터 사용가능함으로, 이 문법 채택시엔 매우 신중해야겠습니다.

#참고
- https://stackoverflow.com/questions/20322740/odd-css-syntax-class-icon-class-icon
Doug님 답변
- http://caniuse.com/#feat=css-sel3
