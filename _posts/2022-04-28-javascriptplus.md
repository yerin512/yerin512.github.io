---
layout: post
title: 자바스크립트 응용 (한입 크기로 잘라 먹는 리액트)
subtitle: 한입 크기로 잘라 먹는 리액트
categories: JavaScript
tags: [TIL, JavaScript]
---





# 단락회로 평가

const getName = (person) => {
 if(!person){
    return "객체가 아닙니다"
  }
  return person.name
}

단락회로 평가

const getName = (person) => {
   const name = person && person.name;
   return name || "객체가 아닙니다."
};

# 조건문 업그레이드


```javascript 

// 평소에 쓰던 거
function isKoreanFood(food) {
 if(food === "불고기" || food === "비빔밥" || food === "떡볶이") { return true }
 return false;
}

console.log(isKoreanFood("불고기");
console.log(isKoreanFood("똠양꿍");

```


```javascript 

// 업그레이드
function isKoreanFood(food) {
 if(["불고기", "비빔밥", "떡볶이"].includes(food)) { return true }
 return false;
}

```

## 음식 고르기


```javascript 

// 평소에 쓰던거
const getMeal = (mealType) => {
 if(mealType === "한식") return "불고기";
 if(mealType === "양식") return "파스타";
 if(mealType === "중식") return "멘보샤";
 if(mealType === "알식") return "초밥";
  return "굶기"
}
console.log("한식");
console.log("중식");

```


```javascript 

// 업그레이드
const meal = {
 한식: "불고기",
 중식: "멘보샤",
 일식: "초밥",
 양식:"스테이크",
 인도식:"카레"
}

const getMeal = (mealType) => {
   return meal[mealType] || "굶기";
};

console.log(getMeal("중식"));
console.log(getMeal());

```


# 비 구조화 할당

```javascript


let arr = ["one", "two", "three"];

let one = arr[0];
let two = arr[1];
let three = arr[2];

// console.log(one, two, three); // one two three

```

업그레이드 

```javascript


let arr = ["one", "two", "three"];

let [one, two, three] = arr;

// console.log(one, two, three); // one two three

```

한 번 더 업그레이드
배열의 선언분리 비 구조 할당화

```javascript


let [one, two, three] = ["one", "two", "three"];
// console.log(one, two, three); // one two three

```


```javascript


let [one, two, three, four='' ] = ["one", "two", "three"];
// console.log(one, two, three, four); // one two three ""

```

기본값 설정 안 해주면 undfined 뜬다


서로 값 바꾸기

'''javascript

let a = 10;
let b = 20;
let tmp = 0;

tmp = a; // 값을 저장해놓고
a= b;
b = tmp;
console.log(a, b) // 20 10

```

업그레이드 

```javascript

let a = 10;
let b = 20;

[a, b] = [b, a];
console.log(a, b);

```

객체에다가

```javascript

let object = { one: "one", two: "two", three: "three" };

let one = object["one"];
let two = object.two;
let three = object.three;

console.log(one, two, three); // one two three

```

```javascript

let object = { one: "one", two: "two", three: "three" };

let { one, two, three } = object;


console.log(one, two, three); // one two three

```

객체의 비구조화 할당은 index값이 아닌 키값을 이용한다.



# Spread 연산자

```javascript


const 빵 = ["단팥", "크림"];
const 쿠키 = ["초코", "바닐라", "딸기"];

const 먹자 = [...빵, "닭가슴살", ...쿠키];

```

중복 제거 
const 베프 = ["예린", "지윤"];
const 개구리 = ["예린", "예은", "유라", "승희"];


const 우리는칭구 = [...베프, "새퀴", ...개구리];

console.log(Array.from(new Set(우리는칭구)));
