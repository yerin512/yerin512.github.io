---
layout: post
title: window.open() 후, 창 닫힘 감지하는 법
subtitle: beforeunload
categories: JavaScript
tags: [TIL, JavaScript]
---


# window.open() 후, 창 닫힘 감지
어떤 api로 파라미터를 보낸 다음에 response로 원하는 result값을 받으면 새창이 뜨게 만들라고 하셨다.
새삼 window 관련 이벤트들을 내가 안 써봤구나... 싶었다.
자바스크립트 공부를 열심히 해야겠다.

### 문법

```javascript

var ret = window.open(url, name, specs, replace);
사용예시
const w = window.open(
        data.message,  //새 창의 url. 
        'normalduck.log', //새로 열릴 창의 속성 또는 창의 이름 
        'width=430,height=500,location=no,status=no,scrollbars=yes',
      );
```

이렇게 하면 새로운 창이 빰! 열린다. 그리고 이 창을 닫았을 때
이를 감지할 수 있는 함수도 있었다.

# beforeunload

이 이벤트를 쓰는 경우는 보통 정말 이 창을 닫으시겠습니까? 라는 얼럿창을 띄울 때?
경우가 있을 거 같다.

### 문법

```javascript
> window.addEventListener('beforeunload', (event) => {
  // 표준에 따라 기본 동작 방지
  event.preventDefault();
  // Chrome에서는 returnValue 설정이 필요함
  event.returnValue = '';
});
```

mdn의 문법을 그대로 가져왔다.

### 사용예시

```javascript

 w.onbeforeunload = function () {
        console.log('닫혔다..!');
위에 window.open() 함수를 변수 w로 주고 사용해보았다.
정말 공부할게 많구나!!!

```
