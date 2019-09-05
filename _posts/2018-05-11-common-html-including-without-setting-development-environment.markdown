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
