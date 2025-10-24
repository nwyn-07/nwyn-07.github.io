---
title: "OOP trong Java - Cơ bản đến nâng cao"
date: 2024-01-16
draft: false
categories: ["Java"]
tags: ["oop", "java", "object-oriented"]
description: "Tìm hiểu về Lập trình Hướng Đối tượng trong Java"
cover:
  image: "images/oop.jpg"
  alt: "Java OOP"
---

Lập trình Hướng Đối tượng (OOP) là phương pháp lập trình dựa trên các đối tượng.

## 4 Tính chất của OOP

### 1. Tính đóng gói (Encapsulation)
```java
public class BankAccount {
    private double balance;
    
    public double getBalance() {
        return balance;
    }
    
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}
```
### 2. Tính kế thừa (Inheritance)
```java
class Animal {
    void speak() { 
        System.out.println("Animal speaks"); 
    }
}

class Dog extends Animal {
    @Override
    void speak() { 
        System.out.println("Woof!"); 
    }
}
```
### 3. Tính đa hình (Polymorphism)
```java
Animal myAnimal = new Dog();
myAnimal.speak(); // Output: "Woof!"
```
### 4. Tính trừu tượng (Abstraction)
```java
abstract class Shape {
    abstract double calculateArea();
}

class Circle extends Shape {
    double radius;
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```
## Ứng dụng thực tế
Xây dựng hệ thống phần mềm lớn

Code dễ bảo trì và mở rộng

Tái sử dụng code hiệu quả