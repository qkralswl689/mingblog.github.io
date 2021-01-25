---
layout: post
title: "jQuery - 1"
date: 2021-01-25
category : [HTML+CSS+JavaScript]
comments: true
---

##### * jQuery 기본
```
 - jQuery - JS 라이브러리
         - JS 프로그래밍을 단순화 해준다
         - HTML <head> 태그 사이에 <script src="jquery-3.5.1.min.js"></script> 을 넣어준다 </head>

 - jQuery Selector
    : HTML Element에 접근하는 메소드
    : $() : jQuery function ($함수)
    : $(선택자) - jQuery DOM

    EX)

      - $(document) / $(window)

      - document.querySelector(".class-name") -> javascript
        $('.class-name') -> jQuery

      - document.querySelectorAll('.class-name') -> javascript
        $('.class-name') -> jQuery

 - jQuery Event Method(listener)
   : on()

 - JavaScript / jQuery 실행 시점
    : HTML Element가 먼저 로딩이 된 이후에 실행되어야 제대로 적용

    (** css : 실행시점과 상관없이 항상 모니터링하고 있기 때문에 해당 HTML Element가 있으면 항상 적용된다)

    - $(document).ready() : HTML 콘텐츠 요소들이 모두 로딩된 후 실행되도록 해주는 함수 메소드
      EX) EX) $(document).ready(function(){
         // 실행 코드
         });

         = 같은 기능 인데 코드의 모양이 다르다 -> 편한거 쓰면된다

         $(function(){
          // 실행코드
         });
  - jQuery DOM 참색
     : 부모
       - parent()
       - parents()
     : 자식
       - childeren()
       - find()
     EX)
     html
     : <div class="parent">
          <div>HTML</div>
          <div>CSS</div>
          <div>Javascript</div>
      </div>

     jquery
     :$(function(){
        console.log( $('.parent').children()[0] );
        console.log( $('.parent').children()[1] );
        console.log( $('.parent').children()[2] );  
      });

      => 출력
      - html
      - css
      - JavaScript



















 - 노드 관계 : 노드 트리의 노드는 서로 계층적 관계를 갖는다

 html - 루트노드 , 최상위 노드 이기 때문에 부모요소가 없다
 head - html 의 첫번재 자식
 body - html의 마지막 자식

innerHTML = property => 값을할당할 때 마다 업데이트 된다 -> w3schools(JavaScript-html dom methods)


bom - 브라우저를 객체화 시켜 컨트롤

JavaScript Window Location - 주소관련 내용이 담겨있는 객체
JavaScript Window Navigator - 브라우저 자체정보

AJAX - 페이지를 다시로드(새로고침)하지 않고 웹 페이지 업데이트
     - 비동기 방식
     - 프로그래밍 언어가 아니다

Framework(프레임워크) - 내가 만든 코드가 포함되는것(서브가 되는것) => 내가 만든 코드가 하나의 함수가 되어서 호출되어 사용되는것
Library(라이브러리) - 내가 만든 코드 안으로 가지고들어오는것 => 내가 만든코드가 메인이 된다
Plug-in(플러그인) - 어떠한 동작을 특화시켜놓은 코드모음 EX) jquery slider plugin 구글검색 하면 해당되는 코드를 찾을 수 있다

```
