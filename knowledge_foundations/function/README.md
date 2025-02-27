# HÀM (FUNCTIONS) TRONG JAVASCRIPT

Hàm là một khối mã được thiết kế để thực hiện một nhiệm vụ cụ thể và có thể tái sử dụng nhiều lần. Hàm giúp mã nguồn trở nên gọn gàng, dễ đọc và dễ bảo trì hơn.

## 1. Khai báo hàm
Hàm có thể được khai báo bằng từ khóa `function` theo cú pháp sau:
```javascript
function tongHaiSo(a, b) {
    return a + b;
}
let ketQua = tongHaiSo(5, 3);
console.log(ketQua); // 8
```
Trong ví dụ trên, hàm `tongHaiSo` nhận hai tham số `a` và `b`, sau đó trả về tổng của chúng.

## 2. Các cách khai báo hàm khác
Ngoài cách khai báo hàm truyền thống, JavaScript còn hỗ trợ nhiều cách khai báo hàm khác:

### 2.1. Hàm biểu thức
Hàm biểu thức là hàm được gán cho một biến:
```javascript
let hamBieuThuc = function(a, b) {
    return a + b;
};
console.log(hamBieuThuc(5, 3)); // 8
```
Hàm biểu thức có thể được sử dụng như bất kỳ biến nào khác.

### 2.2. Hàm mũi tên (Arrow Function)
Hàm mũi tên có cú pháp ngắn gọn hơn và không có `this` riêng:
```javascript
let hamMuiTen = (a, b) => a + b;
console.log(hamMuiTen(5, 3)); // 8
```
Hàm mũi tên thường được sử dụng trong các hàm callback.

### 2.3. Hàm ẩn danh
Hàm ẩn danh là hàm không có tên và thường được sử dụng ngay lập tức:
```javascript
(function() {
    console.log("Đây là hàm ẩn danh");
})();
```
Hàm ẩn danh thường được sử dụng để tạo ra một phạm vi riêng biệt.

### 2.4. Hàm tạo (Constructor Function)
Hàm tạo được sử dụng để tạo đối tượng mới:
```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}
let person1 = new Person("John", 25);
console.log(person1.name); // John
```
Hàm tạo thường được sử dụng trong lập trình hướng đối tượng.

## 3. Hàm đệ quy (Recursive Function)
Hàm đệ quy là hàm tự gọi chính nó để giải quyết bài toán:
```javascript
function giaiThua(n) {
    if (n === 0) {
        return 1;
    }
    return n * giaiThua(n - 1);
}
console.log(giaiThua(5)); // 120
```
Hàm đệ quy cần có điều kiện dừng để tránh vòng lặp vô hạn.

## 4. Hàm callback
Hàm callback là hàm được truyền vào như một đối số của hàm khác:
```javascript
function xinChao(name, callback) {
    console.log("Xin chào " + name);
    callback();
}
function loiChao() {
    console.log("Chào mừng bạn đến với JavaScript!");
}
xinChao("Alice", loiChao);
```
Hàm callback thường được sử dụng trong các tác vụ bất đồng bộ.

## 5. Hàm thuần (Pure Function)
Hàm thuần là hàm không có tác dụng phụ và luôn trả về cùng một kết quả với cùng một đầu vào:
```javascript
function congHaiSo(a, b) {
    return a + b;
}
console.log(congHaiSo(2, 3)); // 5
```
Hàm thuần giúp mã nguồn dễ kiểm tra và bảo trì hơn.

## **Kết luận**
Bài viết này đã cung cấp những kiến thức cơ bản và nâng cao về hàm trong JavaScript. Hiểu rõ về hàm sẽ giúp bạn viết mã nguồn hiệu quả và dễ bảo trì hơn.
