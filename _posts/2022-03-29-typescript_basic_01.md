---
layout: post
title: 타입스크립트 기본 타입
subtitle: 타입스크립트 interface
categories: TypeScript
tags: [TIL, TypeScript]
---



```typescript
interface User {
    age: number,
    name: string,
}
```

인터페이스는 상호 간에 정의한 약속 혹은 규칙을 의미함.

- 객체의 스펙(속성과 속성의 타입)
- 함수의 파라미터
- 함수의 스펙(파라미터, 반환 타입 등)
- 배열과 객체를 접근하는 방식
- 클래스



```typescript
// 변수에 인터페이스 활용
var seho: User = {
    age: 33,
    name: '세호'
}

```typescript
// 함수에 인터페이스 활용

function getUser(user: User) {
    console.log(user);
}

const capt = {
    name: '캡틴',
    age: 100
}

getUser(capt);


// 함수의 스펙(구조)에 인터페이스를 활용

interface SumFunction {
    (a: number, b: number): number;
}

var sum: SumFunction;

sum = function (a: number, b: number): number {
    return a + b;
}

// 인덱싱
interface StringArray {
    [index: number]: string;
}

var arr: StringArray = ['a', 'b', 'c'];
// arr[0] = 'a';

// 딕셔너리 패턴

interface StringRegexDictionary {
    [key: string]: RegExp;
}

var obj: StringRegexDictionary = {
    // sth: /abc/
    cssFile: /\.css$/,
    jsFile: /\.js$/,
}

// obj['cssFile'] = 'a' //오류

Object.keys(obj).forEach(function (value) {
    
})
```
### 인터페이스 확장

```typescript

// 인터페이스 확장
interface Person{
    name: string;
    age: number;
}

interface Developer extends Person{
    hobby: string;
}


var yerin: Developer = {
    hobby: '자는거',
    name: '예린',
    age: 15,
}

```
