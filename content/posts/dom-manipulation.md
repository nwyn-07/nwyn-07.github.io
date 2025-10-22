---
title: "DOM Manipulation - Thao tác với Document Object Model"
date: 2024-01-22
draft: false
categories: ["JavaScript"]
tags: ["dom"]
description: "Hướng dẫn toàn diện về thao tác DOM với JavaScript"
---

DOM (Document Object Model) là giao diện lập trình cho HTML documents.

## Selecting Elements
```javascript
// Theo ID
const header = document.getElementById('header');

// Theo class
const items = document.getElementsByClassName('item');

// Modern methods
const element = document.querySelector('#main .item');
const elements = document.querySelectorAll('.item');
```
## Creating Elements
```javascript
// Tạo element mới
const newDiv = document.createElement('div');
newDiv.className = 'container';
newDiv.textContent = 'Hello World!';

// Thêm vào DOM
document.body.appendChild(newDiv);
```
## Event Handling
```javascript
const button = document.querySelector('button');
button.addEventListener('click', function(event) {
    console.log('Button clicked!', event);
});

// Event delegation
document.addEventListener('click', function(event) {
    if (event.target.matches('.delete-btn')) {
        event.target.parentElement.remove();
    }
});
```
## Form Handling
```javascript
const form = document.querySelector('#user-form');

form.addEventListener('submit', function(event) {
    event.preventDefault();
    
    const formData = new FormData(form);
    const username = formData.get('username');
    const email = formData.get('email');
    
    // Validation
    if (!username || !email) {
        alert('Please fill all fields');
        return;
    }
    
    console.log('Form data:', { username, email });
});
```
## Ứng dụng
Dynamic web applications

Form validation

Interactive UI

Single Page Applications