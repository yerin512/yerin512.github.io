

---
layout: post
title: TypeScript Interface
subtitle:  TypeScript 3강
categories: TypeScript
tags: [TIL, TypeScript]
---

// implements

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
