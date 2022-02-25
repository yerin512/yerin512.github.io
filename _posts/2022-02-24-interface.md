---
layout: post
title: TypeScript Interface
subtitle:  TypeScript 3강
categories: TypeScript
tags: [TIL, TypeScript]
---

# 03 interface - implements

```typescript

interface Car {
	color : string;
	wheels: number;
	start(): void;
}

interface Benz extends Car {
	door: number;
	stop(): void;
	color: ‘black’;
	wheels : 3;
	start(){
	conosle.log(‘gogogo~~’);

}
	

class BMW implements Car {
	color;
	wheels = 4;
	constructor(c:string){
		this.color = c;
	}
	start(){
		console.log(‘go…’);
	}
}

const b = new Bmw(‘green’);
console.log(b);

Bmw : {
	“wheels”: 4,
	“color”: “green”
}

b.start(); // “go..”

```


```typescript

interface Car {
	color: string;
	wheels: number;
	start(): void;
}

interface Toy {
	name : string;
}

interface ToyCar extends Car, Toy {
	price : number;
}

```


# 04 함수



  // 선택적 매개변수, 필수적 매개변수

```
  function add(num1: number, num2: number): void {
    num1 + num2;
  }
  
  function hello(name?: string) {
    return `hello, ${name || "world"}`;
  }

  function hello2(name = "world") {
    return `hello, ${name}`;
  }

  // 선택적 매개변수가  필수적 매개변수보다 앞에 오면 안 된다.

  // function hello3(name?: string, age: number) {
  //   return `hello, ${name} ${age}세`;
  // } // 오류

  // 하지만 옵셔널 매개변수를 앞에두고 싶다면| undefined를 붙여주고 인자에 undefined를 넣어준다.

  function hello4(name: string | undefined, age: number) {
    return `hello, ${name} ${age}세`;
  } // 오류

  console.log(hello4(undefined, 15));


  // # 매개변수를 몇개 받을지 모를때
  
  function add2(...nums: number[]) {
    return nums.reduce((result, num) => result + num, 0);
  }

  add2(1, 2, 3);
  add2(1, 2, 3, 4, 5, 6, 7);


  // # this
  
  interface User {
    name: string,
  }

  const Sam: User = { name: 'Sam' };

  function showName(this: User, age: number, gender: 'm' | 'f') {
    console.log(this.name, age, gender)
  }

  const a = showName.bind(Sam);
  a(30, 'm');
  
  
  interface User2 {
    name: string;
    age: number;
  }
  
  function join2(name: string, age: string): string;
  function join2(name: string, age: number): User2;
  function join2(name: string, age: number | string): User2 | string {
    if (typeof age === "number") {
      return {
        name,
        age,
      };
    } else {
      return "나이는 숫자로 입력해주세요";
    }
  }
}
  
const sam: User2 = join2("Sam", 30);
const jane: string = join2("Jane", "30");


```
