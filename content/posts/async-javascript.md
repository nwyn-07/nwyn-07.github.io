---
title: "Async/Await và Promise trong JavaScript"
date: 2024-01-21
draft: false
categories: ["JavaScript"]
tags: ["async"]
description: "Làm chủ lập trình bất đồng bộ với Async/Await và Promise"
cover:
  image: "images/async.jpg"
  alt: "Async Await illustration"
---

Lập trình bất đồng bộ giúp xử lý các tác vụ mất thời gian mà không chặn luồng chính.

## Promise
```javascript
function getUser(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId) {
                resolve({ id: userId, name: "John" });
            } else {
                reject("User ID is required");
            }
        }, 1000);
    });
}

// Sử dụng Promise
getUser(123)
    .then(user => console.log("User:", user))
    .catch(error => console.error("Error:", error));
```
## Async/Await
```javascript
async function fetchUserData(userId) {
    try {
        const user = await getUser(userId);
        const posts = await getPosts(user.id);
        return { user, posts };
    } catch (error) {
        console.error("Failed to fetch data:", error);
        throw error;
    }
}

// Sử dụng
fetchUserData(123)
    .then(data => console.log(data));
```
## Xử lý lỗi
```javascript
async function safeApiCall() {
    try {
        const result = await potentiallyFailingApi();
        return { success: true, data: result };
    } catch (error) {
        return { success: false, error: error.message };
    }
}
```
## Ưu điểm
Code dễ đọc, dễ bảo trì

Xử lý lỗi tập trung

Hỗ trợ tốt cho API calls