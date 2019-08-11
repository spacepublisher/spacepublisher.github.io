---
layout: post
title:  "Slick.js IE8 이슈"
date:   2018-10-21 00:00:00 +0900
categories: jekyll update
---
캐러셀(현업에서는 '롤링'으로 많이 불리우는) 작업을 하다보면, 웬만한 경우는 직접 만들기보단 플러그인을 씁니다. 정말 특별한 경우가 아니라면, 플러그인 사용을 저는 권장합니다. 제이쿼리 캐러셀 라이브러리야 어마어마하게 많습니다만, 제가 많이 사용한건 [Slick][link1]입니다. 모바일이건, PC웹이건 별 탈없이 무난히 잘 돌아가고, 제가 느끼기에 디자인 커스터마이징 하기 좋게 잘 되어 있었습니다.

## IE8 이슈 발견
그러나, 이번에 IE8까지 크로스브라우징하는 프로젝트에서 문제를 발견했습니다. IE9 ~ Edge는 모두 다 정상 작동 합니다만, 유독 IE8에서 작동이 안됬습니다. 당황스러웠지만, 당황하지않고 구글링, 다음링, 네이버링등을 하여 선구자들의 솔루션을 검색했습니다.

## 데모 사이트에서 직접 다운
결론적으로, 해결했습니다. 코드 수정으로 해결한것은 아닙니다. 공식 사이트에서 제공하는 다운로드 파일 대신 개발자 도구 열고 직접 다운로드해야합니다.   

## 다운로드 경로
현재(2018.10.21) 경로는 다음과 같습니다.   
[http://kenwheeler.github.io/slick/slick/slick.js][link2]

## 안되면, 여기서 다운
공식 사이트에서 직접 다운로드 받는것이 좋지만, 언제 또 바뀔지 모르는 일이기에 화석처럼 제가 한 부를 가지고 있습니다. 혹여나 안되면 저의 구글 드라이브 공유를 이용하십시오.   
[https://drive.google.com/file/d/156U0tqoCIIw0tbRebZmA0zj2tiDyMyC4/view?usp=sharing][link3]

## Special Thx2...
결정적 도움이 된 [zoobley][link4]님에게 감사드립니다.

[link1]: http://kenwheeler.github.io/slick/
[link2]: http://kenwheeler.github.io/slick/slick/slick.js
[link3]: https://drive.google.com/file/d/156U0tqoCIIw0tbRebZmA0zj2tiDyMyC4/view?usp=sharing]
[link4]: https://zoo79.tistory.com/13
