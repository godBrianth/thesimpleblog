---
date: '2025-10-03T22:06:15+07:00'
draft: false
title: 'Lập trình hướng đối tượng (OOPs) trong Java'
description: "Lập trình hướng đối tượng (Object Oriented Programing – OOP) là một phương pháp để thiết kế một chương trình bởi sử dụng các..."
cascade:
  type: docs
---

## Khái niệm về lập trình hướng đối tượng trong java

Lập trình hướng đối tượng (Object Oriented Programing – OOP) là một phương pháp để thiết kế một chương trình bởi sử dụng các lớp và các đối tượng.

Java là một ngôn ngữ lập trình hướng đối tượng vì vậy nó cũng hỗ trợ các đặc tính của lập trình hướng đối tượng:

* Đa hình (Polymorphism)
* Thừa kế (Inheritance)
* Đóng gói (Encapsulation)
* Trừu tượng (Abstraction)

## Đối tượng

Đối tượng là một thực thể có trạng thái và hành vi. Nó có thể mang tính vật lý hoặc logic.

Nếu chúng ta xem xét thực tế chúng ta có thể tìm thấy nhiều đồ vật xung quanh chúng ta: cái bàn, con chó, con người, v.v… Tất cả các đối tượng này đều có thuộc tính và hành vi.

Nếu chúng ta xem xét một con chó, thuộc tính của nó sẽ là – tên, giống, màu sắc, và các hành vi là: sủa, chạy, ăn, … Nếu bạn so sánh các đối tượng trong phần mềm với một đối tượng trong thế giới thực, chúng sẽ có đặc điểm rất giống nhau: thuộc tính đối tượng trong phần mềm được lưu trữ trong trường (field) và hành vi được lưu trữ trong phương thức (method).

## Lớp (Class)

Chúng ta có thể xem lớp như một khuôn mẫu (template) của đối tượng (Object). Trong đó bao gồm dữ liệu của đối tượng (fields hay properties) và các phương thức(methods) tác động lên thành phần dữ liệu đó gọi là các phương thức của lớp.

## Sự khác nhau giữa lớp và đối tượng trong java

| Đối tượng | Lớp |
| :--- | :--- |
| Đối tượng là thể hiện của 1 lớp. | Lớp là một khuôn mẫu hay thiết kế để tạo ra các đối tượng. |
| Đối tượng là 1 thực thể trong thế giới thực như Con mèo (Cat), con chó (Dog), ... | Lớp là một nhóm các đối tượng tương tự nhau. Ví dụ: Lớp động vật (Animal). |
| Đối tượng là 1 thực thể vật lý | Lớp là 1 thực thể logic |
| Đối tượng được tạo ra chủ yếu từ từ khóa **new**. Ví dụ: `Student s1=new Student();` | Lớp được khai báo bằng việc sử dụng từ khóa **class**. Ví dụ: `class Student{}` |
| Đối tượng có thể được tạo được tạo nhiều lần. | Lớp được khai báo 1 lần duy nhất. |
| Đối tượng được cấp bộ nhớ khi nó được tạo ra. | Lớp không được cấp bộ nhớ khi nó được tạo ra. |
| Có rất nhiều cách để tạo ra đối tượng trong java như từ khóa **new**, phương thức **newInstance()**, phương thức **clone()**, phương thức **factory** và **deserialization**. | Chỉ có một cách để định nghĩa lớp trong java sử dụng từ khóa **class**. |

## Package

### Định nghĩa

Một package (gói) trong java là một nhóm các kiểu tương tự của các lớp, giao diện và các package con .

Package trong java có thể được phân loại theo hai hình thức, package được dựng sẵn và package do người dùng định nghĩa.

Có rất nhiều package được dựng sẵn như java, lang, net, io, util, sql, …

### Package do người dùng tự định nghĩa

Cú pháp:

`package <tên package cha>[.<tên package con>];`

Ví dụ về java package:

`package gpcoder; // Package cha`

Lợi thế của việc sử dụng package trong java:

* Package được sử dụng để phân loại lớp và interface giúp dễ dàng bảo trì.
* Package cung cấp bảo vể truy cập
* Package khắc phục được việc đặt trùng tên.

### Truy cập package từ package khác

Có 3 cách để truy cập package từ package bên ngoài:

* Khai báo import package.*; tránh sử dụng cách này, không xác định sẽ sử dụng class nào, có thể gặp vấn đề trùng tên lớp nếu cả 2 package import package.* giống nhau. Ví dụ: sử dụng class Date có thể gặp lỗi biên dịch do không thể xác định chính xác sử dụng class Date của package nào nếu import cả 2 package java.util và java.sql.

* Khai báo import package.ClassName; nên sử dụng cách này để giữ code đơn giản, rõ ràng, tái sử dụng lại nhiều chỗ, hạn chế xung đột về tên.

* Sử dụng tên đầy đủ: tránh sử dụng cách này, do code trở nên dài dòng nếu package gồm nhiều cấp cha, con.

## Phạm vi truy cập (Access modifier)

Có hai loại modifier trong java: **access modifiers** và **non-access modifiers**.

Các access modifiers trong java xác định độ truy cập (Phạm vi) vào dữ liệu của của các trường (field), phương thức (method), cấu tử (constructor) hoặc lớp (class).

Có 4 kiểu của java access modifiers:

* private
* (Mặc định)
* protected
* public
Và có một vài non-access modifiers chẳng hạn static, abstract, synchronized, native, volatile, transient, v.v.. Trong tài liệu này chúng ta sẽ học về access modifier.

Bảng mô tả tổng quan về cách sử dụng các access modifier:

| Access Modifier | Truy cập bên trong class? | Truy cập bên trong package? | Truy cập bên ngoài package bởi class con? | Truy cập bên ngoài class và không thuộc class con? |
| :--- | :---: | :---: | :---: | :---: |
| **private** | Y | | | |
| **Default** | Y | Y | | |
| **protected** | Y | Y | Y | |
| **public** | Y | Y | Y | Y |

Tài liệu tham khảo:

* https://www.javatpoint.com/java-oops-concepts
* https://www.tutorialspoint.com/java/java_packages.htm