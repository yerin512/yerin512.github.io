---
layout: post
title: strict mode
subtitle:  Deep DIve 20장
categories: JavaScript
tags: [TIL, JavaScript, DeepDive]
---


# strict mode


## strict mode란?

```javascript

function foo () {
 x = 10;
}
foo();

console.log(x);

```

foo 함수내에 선언하지않은 x 변수에 값 10을 할당 하면
자바스크립트엔진은  x 변수가 어디서 선언되었는지 스코프 체인을 통해 검색하기 시작한다.
우선 foo 함수 스코프에서 검색할 것이고, 그 다음 상위 스코프 (예제에선 전역 스코프)에서 변수 선언을 검색한다.
없기때문에 ReferenceError를 발생시킬거같지만 자바스크립트 엔진은 암묵적으로 전역 객체에 x 프로퍼티를 동적 생성한다. 이때 전역 객체의 x 프로퍼티는 마치 전역 변수처럼 사용할 수 있다.
이러한 현상을 암묵적 전역이라한다.
암묵적 전역은 오류를 발생시킬 원인이 된다. 반드시 var, let, const 키워드를 사용해 변수를 선언해야한다.

오타, 문법 실수로 인한 오류를 줄여주기 위해 es5부터 strict mode(엄격모드)가 추가됏다.

ESLint같은 린트 도구를 사용해도 유사한 효과를 얻을 수 있다.
린트 도구는 정적 분석 기능을 통해 소스코드를 실행하기 전에 소스코드를 스캔해
문법적 오류만 아니라 잠재적 오류를 찾아내고 오류의 원인을 리포팅해준다.

린트도구는 strict mode가 제한하는 오류는 물론 
코딩 컨벤션을 설정 파일로 정의하고 강제할 수 있기 때문에 더욱 강력한 효과를 얻을 수 있다.

ES6에서 도입된 클래스와 모듈은 기본적으로 strict mode가 적용된다.

## 20.2 strict mode의 적용

strict mode를 적용하려면 전역의 선두 또는 함수 몸체의 선두에 'use strict'; 를 추가한다.
코드의 선두에 위치하지않으면 제대로 동작하지 않는다.

## 20.3 전역에 strict mode를 적용하는 건 피하자.

다른 스크립트에 영향을 주지않고 해당 스크립트에만 한정되어 적용된다.
하지만 strict mode 스크립트와 non-strict mode 스크립트를 혼용하는 건 오류를 발생시킬수 이다.
외부 서드파티 라이브러리를 사용하는 경우는 특히 라이브러리가 non-strict mode인겨 경우도 있기 때문에 전역에 strict mode사용하는건 바람직하지않다.
즉시 실행함수로 스크립트 전체를 감싸서 스코프를 구분하고 즉시 실행함수 선두에 strict mode를 적용한다.


전역에 적용한 strict mode는 스크립트 단위로 적용된다.
따라서 strict mode는 즉시 실행 함수로 감싼 스크립트 단위로 적용하는 것이 바람직하다.



```javscript

// 즉시 실행 함수의 선두에 strict mode 적용
(function () {
 'use strict';

}());
```

## 20.4 함수 단위로 strict mode를 적용하는 것도 피하자

어떤 함수는 strict mode를 사용하고 어떤 함수는 strict mode를 사용하지 않는것은 바람직하지않고
모든 함수에 일일이 strict mode를 적용하는 것은 번거롭다.
그리고 strict mode가 적용된 함수가 참조할 함수 외부의 컨텍스트에 strict mode를 적용하지않는다면 이또한 문제가 될 수있다.

## 20.5 strict mode가 발생시키는 에러

strict mode적용했을떄 에러가 발생하는 대표적인 사례

### 20.5.1 암묵적 전역

선언하지않은 변수를 참조하면 ReferenceError가 발생한다.

```javascript

(function () {
 'use strict';

x = 1;
console.log(x);
}(); // ReferenceError : x is not defined

```


### 20.5.2 변수, 함수, 매개변수의 삭제

delete 연산자로 변수 함수 매개변수를 삭제하면 StntaxError가 발생한다

### 20.5.3 매개변수 이름의 중복

중복된 매개변수 이름을 사용하면 SyntaxError가 발생한다.

### 20.5.4 with 문의 사용

with문을 사용하면 SyntaxError가 발생한다. 사용하지 않는게 좋다.

## 20.6 strict mode 적용에 의한 변화

### 20.6.1 일반 함수의 this

strict mode에서 함수를 일반 함수로 호출하면 this에 undefined가 바인딩된다.
생성자 함수가 아닌 일반 함수 내부에서는 this를 사용할 필요가 없기 때문이다.
에러는 발생하지 않는다.

### 20.6.2 arguments 객체

strict mode에서는 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체 반영되지 않는다.












