---
title: "JavaScript ES6+ Features - Những tính năng quan trọng"
date: 2024-01-20
draft: false
categories: ["JavaScript"]
tags: ["es6"]
description: "Khám phá các tính năng mới trong ES6+"
cover:
  image: "images/es6.jpg"
  alt: "JavaScript ES6"
---

ES6 (ECMAScript 2015) mang đến nhiều tính năng hiện đại giúp code JavaScript ngắn gọn và mạnh mẽ hơn.

## Arrow Functions
```javascript
// Traditional function
function multiply(a, b) {
    return a * b;
}

// Arrow function
const multiply = (a, b) => a * b;

// Một tham số
const square = x => x * x;
```
## Template Literals
```javascript
const name = "John";
const age = 25;

// Cách cũ
console.log("Hello " + name + ", you are " + age + " years old");

// Template Literals
console.log(`Hello ${name}, you are ${age} years old`);
```
## Destructuring
```javascript
// Array Destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];

// Object Destructuring
const person = { name: "John", age: 30, city: "Hanoi" };
const { name, age } = person;
```
## Spread Operator
```javascript
// Copy array
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];

// Copy object
const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };
```
## Ưu điểm ES6+
Code ngắn gọn, dễ đọc

Quản lý scope tốt hơn

Hỗ trợ module

Cú pháp hiện đại

