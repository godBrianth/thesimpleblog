---
date: '2025-10-13T23:31:15+07:00'
draft: false
title: 'Spring Boot tutorial chi tiết từ A-Z cho lập trình viên Java'
description: "Spring Framework nổi tiếng nhờ tính mạnh mẽ, linh hoạt, nhưng cũng nổi tiếng với sự phức tạp. Để giải quyết bài toán này, Spring Boot đã..."
cascade:
  type: docs
---

**Spring Framework nổi tiếng nhờ tính mạnh mẽ, linh hoạt, nhưng cũng nổi tiếng với sự phức tạp. Để giải quyết bài toán này, Spring Boot đã ra đời như một phần mở rộng của Spring Framework, được tạo ra để đơn giản hóa quá trình thiết lập và phát triển ứng dụng. Bài hướng dẫn Spring Boot tutorial này sẽ chỉ cho bạn cách cài đặt môi trường phát triển.**

## Cài đặt Java Development Kit (JDK)

JDK là nền tảng cho mọi ứng dụng Java, cung cấp trình biên dịch, thư viện và môi trường thực thi. Spring Boot 3.x yêu cầu Java 17 trở lên.

Để kiểm tra phiên bản hiện tại: Bạn mở Terminal/Command Prompt, gõ lệnh: `java -version`

Nếu chưa có hoặc phiên bản không đúng, hãy cài đặt JDK.

## Hướng dẫn cài đặt JDK

Bạn có thể chọn giữa hai bản thông dụng:

* Oracle JDK: https://www.oracle.com/java/technologies/downloads/
* OpenJDK (khuyến nghị): Ví dụ, Adoptium Temurin tại https://adoptium.net/

Các bước cài đặt:

* Tải bản cài đặt phù hợp với hệ điều hành của bạn (Windows, macOS, Linux) từ một trong các link trên.
* Chạy file cài đặt và làm theo hướng dẫn.
* Thiết lập biến môi trường `JAVA_HOME`:
    * Trỏ `JAVA_HOME` đến thư mục cài đặt JDK (ví dụ: `C:\Program Files\Java\jdk-17`).
    * Thêm `%JAVA_HOME%\bin` (Windows) hoặc `$JAVA_HOME/bin` (macOS/Linux) vào biến `Path` của hệ thống.
* Mở Terminal/Command Prompt mới, kiểm tra lại với `java -version`.

## Cài đặt Maven hoặc Gradle

Các công cụ như Apache Maven và Gradle đều là những hệ thống quản lý build và dependency, có chức năng tự động hóa quá trình biên dịch, đóng gói và quản lý thư viện cho dự án. 

Apache Maven sử dụng tệp `pom.xml` và hoạt động dựa trên quy ước, là một lựa chọn rất phổ biến và quen thuộc trong cộng đồng. Trong khi đó, Gradle mang đến sự linh hoạt cao hơn với việc sử dụng Groovy hoặc Kotlin DSL trong tệp `build.gradle`, đồng thời thường cho tốc độ build nhanh hơn. 

Đối với người mới bắt đầu, Maven thường được khuyên dùng vì tính dễ tiếp cận của nó.

## Hướng dẫn cài đặt Apache Maven

* Bước 1: Tải Maven: https://maven.apache.org/download.cgi
* Bước 2: Giải nén vào một thư mục (ví dụ: `C:\Program Files\Apache\maven`).
* Bước 3: Thiết lập biến môi trường:
    * `M2_HOME` (hoặc `MAVEN_HOME`): Trỏ đến thư mục giải nén Maven.
    * Thêm `%M2_HOME%\bin` (Windows) hoặc `$M2_HOME/bin` (macOS/Linux) vào `Path`.
* Kiểm tra: `mvn -version`.

## Hướng dẫn cài đặt Gradle

* Bước 1: Tải Gradle: https://gradle.org/install/
* Bước 2: Làm theo hướng dẫn trên trang chủ hoặc giải nén thủ công.
* Bước 3: Nếu cài manual, thiết lập `GRADLE_HOME` và thêm `$GRADLE_HOME/bin` vào `Path`.
* Kiểm tra: `gradle -version`.

## Cài đặt IDE (Integrated Development Environment)

IDE cung cấp trình soạn thảo code thông minh, debugger và các công cụ hỗ trợ phát triển. Một số IDE phổ biến bao gồm:

**IntelliJ IDEA**: Mạnh mẽ và thông minh với khả năng phân tích và gợi ý code hàng đầu.

* **Community Edition (Miễn phí)**: Đủ dùng cho hầu hết các dự án Spring Boot.
* **Ultimate Edition (Trả phí)**: Nhiều tính năng nâng cao hơn.
* Link tải: https://www.jetbrains.com/idea/download/

**Eclipse IDE + Spring Tools Suite (STS)**: Tích hợp sâu dành riêng cho hệ sinh thái Spring giúp điều hướng và quản lý dự án dễ dàng.

* Tải Eclipse IDE for Java Developers: https://www.eclipse.org/downloads/packages/
* Cài STS từ Eclipse Marketplace (Help -> Eclipse Marketplace -> tìm “Spring Tools”) hoặc tải bản tích hợp sẵn từ https://spring.io/tools.

**Visual Studio Code (VS Code) + Extensions**: Nhẹ, nhanh và linh hoạt hơn.

* Tải VS Code: https://code.visualstudio.com/download
* Cài đặt các extension: “Extension Pack for Java” (Microsoft) và “Spring Boot Extension Pack” (VMware).

Sau khi hoàn thành các bước trên, môi trường của bạn đã sẵn sàng để bắt đầu với Spring Boot!