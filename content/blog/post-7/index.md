---
date: '2025-10-15T23:31:15+07:00'
draft: false
title: 'Hiểu rõ về JSON là gì? Cách lấy dữ liệu từ JSON'
description: "JSON là viết tắt của JavaScript Object Notation, là một kiểu định dạng dữ liệu tuân theo một quy luật nhất định mà hầu hết các ngôn..."
cascade:
  type: docs
---

## JSON là gì?

JSON là viết tắt của JavaScript Object Notation, là một kiểu định dạng dữ liệu tuân theo một quy luật nhất định mà hầu hết các ngôn ngữ lập trình hiện nay đều có thể đọc được. JSON là một tiêu chuẩn mở để trao đổi dữ liệu trên web.

![](json-vs-xml-588x420.png)

## Định nghĩa

Định dạng JSON sử dụng các cặp `key` – `value` để dữ liệu sử dụng. Nó hỗ trợ các cấu trúc dữ liệu như đối tượng và mảng. Ví dụ một tập tin có tên `topdev_info.json` với nội dung như ở dưới đây sử dụng format kiểu JSON để lưu trữ thông tin:

```
{
    "name" : "TopDev",
    "title" : "Việc làm IT cho Top Developers",
    "description" : "là hệ sinh thái bao gồm cộng đồng các Top Developers."
}
```

Ta có thể thấy cú pháp của JSON có 2 phần đó là `key` và `value`:

* Chuỗi JSON được bao lại bởi dấu ngoặc nhọn {}
* Các `key`, `value` của JSON bắt buộc phải đặt trong dấu nháy kép {“}, nếu bạn đặt nó trong dấu nháy đơn thì đây không phải là một chuỗi JSON đúng chuẩn. Nếu trường hợp trong `value` của bạn có chứa dấu nháy kép `"` thì hãy dùng dấu () để đặt trước nó, ví dụ  `"json là gì"`.
* Nếu có nhiều dữ liệu thì dùng dấu phẩy `,` để ngăn cách.
* Các `key` của JSON bạn nên đặt chữ cái không dấu hoặc số, dấu _ và không có khoảng trắng., ký tự đầu tiên không nên đặt là số.

File json có thể được lưu với bất kỳ phần mở rộng nào, tuy nhiên thông thường thì nó được lưu dưới phần mở rộng là `.json` hoặc `.js`.

Giá trị key trong JSON có thể là chuỗi (string), số (numner), rỗng (null), mảng (array), hoặc đối tượng (object).

## Cấu trúc chuỗi JSON
### Object là gì?

**Object** trong Json được thể hiện bằng dấu ngoặc nhọn {}. Khái niệm Object trong Json cũng khá tương đồng với Object trong Javascript. Tuy nhiên, Object trong Json vẫn có những giới hạn như:

* **Key**: phải luôn nằm trong dấu ngoặc kép, không được phép là biến số.
* **Value**: Chỉ cho phép các kiểu dữ liệu cơ bản: numbers, String, Booleans, arrays, objects, null. Không cho phép function, date, undefined.
* Không cho phép dấy phẩy cuối cùng như Object trong Javascript.

### Kiểu OBJECT

```
var nhat = {
   "firstName" : "Nhat",
   "lastName" : "Nguyen",
   "age" :  "34"
};
```

### Kiểu OBJECT IN ARRAY

```
var employees = [{
   "name" : "Binh",
   "age" :  "38",
   "gender" : "male"
 
},
{
   "name" : "Nhat",
   "age" : "34",
   "gender" : "male"
 
},
{
   "name" : "Nhu",
   "age" : "25",
   "gender" : "female"
}];
```

### Kiểu NEST OBJECT

```
var employees = {
  "hieu" : {
  "name" : "Hieu",
  "age" :  "29",
  "gender" : "male" 
},
 
"nhat" : {
  "name" : "Nhat",
  "age" : "34",
  "gender" : "male"
},
 
"nhu" : {
  "name" : "Nhu",
  "age" : "25",
  "gender" : "female"
}
}
```

## Nên sử dụng JSON khi nào

Đó là khi bạn muốn lưu trữ dữ liệu đơn thuần dưới dạng metadata ở phía server. Chuỗi JSON sẽ được lưu vào database và sau đó khi cần dữ liệu thì sẽ được giải mã. Ví dụ với PHP, nó cung cấp các hàm liên quan đến JSON để mã hóa hoặc giải mã là json_encode và json_decode.

Một trường hợp khá phổ biến trong JavaScript mà dữ liệu được định dạng theo format JSON xuất hiện đó là trong các AJAX request.

Ví dụ bạn tạo tập tin `topdev_info.json` ở thư mục gốc của server (để khi request vào URL `http://localhost/topdev_info.json` thì server trả về nội dung của tập tin này) và sau đó bạn tạo một tập tin `topdev_ajax.html` với nội dung như sau:

```
<html>
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.2/jquery.min.js"></script>
</head>
<body>
<script type="text/javascript">
    $.ajax(
        type: 'GET',
        url: "http://localhost/topdev_info.json",
        success: function(response) {
            console.log("Data type: " + (typeof response));
            console.log("Application name: " + response.name);
        },
    );
</script>
</body>
</html>
```

Đoạn code trên sử dụng `$.ajax()` để gửi AJAX request lên server lấy về nội dung file `topdev_info.json`. Sau khi lấy về nội dung tập tin này thành công, dữ liệu sẽ được chuyển vào biến `response`.

Nếu bạn mở developer console của trình duyệt lên (nhấn phím F12) bạn sẽ thấy kiểu dữ liệu của biến `response` này được JavaScript `object` với các thuộc tính như `name`, `title`, `decription`.