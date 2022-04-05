---
layout: post
title: MouseEvent.clientX
subtitle: MouseEvent.clientX
categories: Javascript
tags: [TIL, Javascript]
---

![image](https://user-images.githubusercontent.com/73337811/161739561-23ac0704-293a-4ca2-a95d-b33928142afc.png)


드림코딩 자바스크립트 브라우저 인강을 보고 있는데 clientX라는 이벤트가 있는지 처음 알았다!

MouseEvent.clientX
MouseEvent 인터페이스의 clientX읽기 전용 속성은 이벤트가
발생한 애플리케이션(viewport) 내에 수평 좌표를 제공한다.

예를 들어 뷰포트의 왼쪽 가장자리를 클릭하면 페이지가 수평으로 스크롤되는지 여부에 관계없이 항상 clientX값이 0인 마우스 이벤트가 발생한다는 것임.

예시

```javascript

var x = instanceOfMouseEvent.clientX
HTML
<p>위치를 보면서 마우스를 이동하십시오</p>
<p id="screen-log"></p>
JavaScript
let screentLog = document.querySelector(#screen-log);
document.addEventListener('mousemove',logkey);

function logKey(e){
screenLog.innerText=`
Screen X/Y: ${e.screenX}, ${e.screenY}
Client X/Y: ${e.clientX}, ${e.clientY}`;
}

```
