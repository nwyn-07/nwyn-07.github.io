---
title: "Java Collections Framework - Toàn tập"
date: 2024-01-18
draft: false
categories: ["Java"]
tags: ["collections", "data-structures", "framework"]
description: "Khám phá Java Collections Framework từ cơ bản đến nâng cao"
cover:
  image: "images/java-collection.png"
  alt: "Java Collection Framework"
---

Collections Framework cung cấp các cấu trúc dữ liệu để lưu trữ và xử lý nhóm đối tượng.

## Các Interface chính

### List - Danh sách có thứ tự
```java
List<String> arrayList = new ArrayList<>();
arrayList.add("Java");
arrayList.add("Python");
arrayList.get(0); // "Java"

List<String> linkedList = new LinkedList<>();
```

### Set - Tập hợp không trùng lặp
```java

Set<String> hashSet = new HashSet<>();

hashSet.add("Apple");

hashSet.add("Apple"); // Bị bỏ qua



Set<String> treeSet = new TreeSet<>(); // Sắp xếp tự động
```

### Map - Ánh xạ key-value
```java

Map<String, Integer> hashMap = new HashMap<>();

hashMap.put("John", 25);

hashMap.put("Jane", 30);

hashMap.get("John"); // 25
```

## So sánh hiệu năng

Collection	Get	Add	Remove	Contains

ArrayList	O(1)	O(1)\*	O(n)	O(n)

LinkedList	O(n)	O(1)	O(1)	O(n)

HashSet	O(1)	O(1)	O(1)	O(1)

## Best Practices
Chọn collection phù hợp với use case

Sử dụng diamond operator <>

Immutable collections khi cần

