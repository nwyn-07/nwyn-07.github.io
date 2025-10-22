---
title: "Xử lý Exception và Debug trong Java"
date: 2024-01-17
draft: false
categories: ["Java"]
tags: ["exception", "debug", "error-handling"]
description: "Hướng dẫn xử lý lỗi và debug trong Java"
---

Xử lý ngoại lệ là kỹ năng quan trọng giúp ứng dụng chạy ổn định và dễ bảo trì.

## Các loại Exception

### Checked Exception (Bắt buộc xử lý)
```java
try {
    FileReader file = new FileReader("file.txt");
} catch (FileNotFoundException e) {
    System.out.println("File not found: " + e.getMessage());
}
```
### Unchecked Exception (Runtime Exception)
```java
try {
    int[] arr = new int[5];
    arr[10] = 100; // ArrayIndexOutOfBoundsException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Invalid array index");
}
```
### Try-with-resources (Java 7+)
```java
try (FileReader reader = new FileReader("file.txt");
     BufferedReader br = new BufferedReader(reader)) {
    String line = br.readLine();
    // Tự động đóng resource
}
```
## Kỹ thuật Debug
Sử dụng breakpoints trong IDE

Debug với System.out.println()

Logging với Log4j/SLF4J
