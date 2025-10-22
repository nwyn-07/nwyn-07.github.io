---
title: "Fetch API và AJAX - Giao tiếp với Server"
date: 2024-01-23
draft: false
categories: ["JavaScript"]
tags: ["api"]
description: "Hướng dẫn sử dụng Fetch API để giao tiếp với server"
---

Fetch API cung cấp interface hiện đại để thực hiện HTTP requests.

## GET Request
```javascript
fetch('https://api.example.com/users')
    .then(response => {
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        return response.json();
    })
    .then(data => {
        console.log('Users:', data);
    })
    .catch(error => {
        console.error('Error:', error);
    });
```
## POST Request
```javascript
fetch('https://api.example.com/users', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify({
        name: 'John Doe',
        email: 'john@example.com'
    })
})
.then(response => response.json())
.then(data => console.log('Success:', data));
```
## Async/Await với Fetch
```javascript
async function fetchUser(userId) {
    try {
        const response = await fetch(`https://api.example.com/users/${userId}`);
        
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        
        const user = await response.json();
        return user;
    } catch (error) {
        console.error('Failed to fetch user:', error);
        return null;
    }
}
```
## Upload File
```javascript
async function uploadFile(file) {
    const formData = new FormData();
    formData.append('file', file);

    try {
        const response = await fetch('/api/upload', {
            method: 'POST',
            body: formData
        });

        if (response.ok) {
            const result = await response.json();
            return result;
        }
    } catch (error) {
        console.error('Upload error:', error);
    }
}
```
## Ưu điểm Fetch API
Cú pháp đơn giản

Hỗ trợ Promise

Linh hoạt với nhiều loại request

Modern replacement cho XMLHttpRequest
