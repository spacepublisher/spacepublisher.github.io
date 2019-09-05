---
layout: post
title:  "개발환경 세팅없이 HTML 공통부분 인클루딩하기"
date:   1988-06-10 00:00:00 +0900
categories: jekyll update
---
PHP나 Java같은 백엔드 개발 언어에는 인클루딩(Including)같은 문법 장치가 필수로 있습니다.  
이를 통해, 공통된 부분을 따로 빼내어 관리하면, 유지보수가 매우 편합니다.  
현대 웹프로젝트의 규모를 생각하면 편함을 넘어서서, 이것 없이는 불가능에 가깝습니다.

## HTML은 인클루딩 문법이 없습니다.
그러나, 순수 HTML은 이러한 문법적 장치가 없습니다. 프로그래밍 언어가 아니기 때문입니다. 마크업 언어입니다.  
사실 퍼블리셔의 컴퓨터에 PHP머신을 설치하면 됩니다. 머신 설치하고, 아파치 세팅하면 됩니다.  
하지만, 그건 말이 쉽지 여러가지 이유로 퍼블리셔들이 그러한 세팅을 하는것은 참 난관이 많습니다.  
프로젝트 초장부터 퍼블리셔 기를 다 빼놓는 사태가 발생할 수도 있습니다.  
당장에 내가 깔면, 동료 퍼블리셔도 동일하게 깔아야 합니다. 이게 생각보다 문제가 많습니다.  
그런점에서, 자바스크립트로 이게 가능하다면 참 좋겠으나, 막상 구현하기에는 생각처럼 잘 안됩니다. 그런게 있으면 참 좋겠다고만 생각했습니다.

## 할 수 있다! 인클루딩
그러나 그것이 실제로 일어났습니다.  
단언컨대, 저의 이번 프로젝트 최대 수확은 바로 이 인클루딩 테크닉을 수확한것입니다.  
이를 활용하면 퍼블리싱 산출물 관리가 매우 편해집니다. 제 생각에는 '혁신'이란 단어가 아깝지 않습니다.

## 코드
구체적인 코드를 공개합니다.  
JS코드를 눈여겨 보십시오.  
특히, 3), 4)는 고칠필요없이 그대로 쓰시면 되고,  
1), 2)를 고쳐서 쓰시면 됩니다.  
1)에서 유니크한 id를 등록하고,  
2)에서 해당 id에 해당하는 상세 마크업을 정의합니다.  

<p data-height="1025" data-theme-id="0" data-slug-hash="jxxqpV" data-default-tab="js,result" data-user="verysomenice" data-embed-version="2" data-pen-title="Including common part using only JS(No PHP, No Java...)" class="codepen">See the Pen <a href="https://codepen.io/verysomenice/pen/jxxqpV/">Including common part using only JS(No PHP, No Java...)</a> by verysomenice (<a href="https://codepen.io/verysomenice">@verysomenice</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

## 참고 사이트
코드 설계 및 1),2),3)은 제가 만들었지만, 핵심 로직인 4)코드는 저의 코드가 아닙니다.  
다음 사이트들을 참고하였습니다.

- [http://tomasz.janczuk.org/2013/05/multi-line-strings-in-javascript-and.html][link1]
- [http://stackoverflow.com/questions/805107/creating-multiline-strings-in-javascript/5571069#5571069][link2]

[link1]: http://tomasz.janczuk.org/2013/05/multi-line-strings-in-javascript-and.html
[link2]: http://stackoverflow.com/questions/805107/creating-multiline-strings-in-javascript/5571069#5571069

## 사족
혹자는 반박하실 수도 있습니다.  
"거 걍 Node깔면 자동화로 척척척 HTML 조립 시켜주는데..."  
저는 이렇게 생각합니다.  
프로젝트를 만드는 사람들의 목적은 '학습'이 아닙니다.  
프로젝트를 만드는 사람들의 목적은 프로젝트의 '성공'입니다.  
신기술이 항상 옳은것은 아닙니다.  
학습 강요는 누군가에게는 고문입니다.  
너무 큰 변화는 조직의 안정성에 금을 만듭니다.  
합리적인 '꼼수'는 강력합니다. 그래서 이 방법이 혁신인겁니다.















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
