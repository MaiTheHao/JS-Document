# LẬP TRÌNH CƠ BẢN VỚI JAVASCRIPT

## 1. Câu lệnh rẽ nhánh: `if - else`
Câu lệnh `if - else` là một cấu trúc điều kiện quan trọng giúp kiểm tra và xử lý các tình huống khác nhau trong chương trình. Khi điều kiện trong `if` đúng (true), khối lệnh bên trong sẽ được thực thi; nếu điều kiện sai (false), chương trình sẽ chạy vào khối `else` (nếu có).

### **Cú pháp:**
```javascript
if (điều kiện) {
    // Khối lệnh thực thi nếu điều kiện đúng
} else {
    // Khối lệnh thực thi nếu điều kiện sai
}
```

> **Lưu ý:** Nếu không cần xử lý khi điều kiện sai, có thể bỏ qua phần `else`.

### **Ví dụ:**
```javascript
let tuoi = 18;
if (tuoi < 18) {
    console.log("Bạn chưa đủ tuổi để vào trang web này");
} else {
    console.log("Bạn đã đủ tuổi để vào trang web này");
}
```
Trong ví dụ trên, chương trình kiểm tra tuổi và đưa ra thông báo phù hợp.

## 2. Vòng lặp trong JavaScript
Vòng lặp giúp thực hiện một khối mã nhiều lần mà không cần phải viết lại đoạn code đó. Dưới đây là các loại vòng lặp phổ biến trong JavaScript.

### **2.1. Vòng lặp `for`
Dùng khi biết trước số lần lặp cụ thể.

### **Cú pháp:**
```javascript
for (khởi tạo biến; điều kiện lặp; thay đổi biến điều khiển) {
    // Khối lệnh cần lặp
}
```

### **Ví dụ:**
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```
- `let i = 0`: Khởi tạo biến `i` bắt đầu từ 0.
- `i < 5`: Lặp khi `i` nhỏ hơn 5.
- `i++`: Tăng `i` sau mỗi lần lặp.

### **Giải thích chi tiết:**
Vòng lặp `for` bắt đầu bằng việc khởi tạo biến `i` với giá trị 0. Sau đó, điều kiện `i < 5` được kiểm tra, nếu đúng, khối lệnh bên trong vòng lặp sẽ được thực thi. Sau mỗi lần thực thi, biến `i` được tăng lên 1 và quá trình lặp lại cho đến khi điều kiện `i < 5` sai.

### **2.2. Vòng lặp `while` và `do while`
Dùng khi không biết trước số lần lặp cụ thể.

### **Cú pháp vòng lặp `while`:**
```javascript
while (điều kiện) {
    // Khối lệnh sẽ thực thi nếu điều kiện đúng
}
```

### **Ví dụ:**
```javascript
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```
Trong ví dụ trên, vòng lặp `while` sẽ tiếp tục thực thi khối lệnh bên trong cho đến khi điều kiện `i < 5` sai.

### **Cú pháp vòng lặp `do while`:**
```javascript
do {
    // Khối lệnh sẽ thực thi ít nhất một lần
} while (điều kiện);
```

### **Ví dụ:**
```javascript
let j = 0;
do {
    console.log(j);
    j++;
} while (j < 5);
```
Vòng lặp `do while` đảm bảo khối lệnh bên trong được thực thi ít nhất một lần trước khi kiểm tra điều kiện.

## 3. Câu lệnh `switch-case`
Câu lệnh `switch-case` giúp thay thế nhiều câu lệnh `if-else` liên tiếp khi kiểm tra một giá trị cụ thể.

### **Cú pháp:**
```javascript
switch (biểu_thức) {
    case giá_trị_1:
        // Khối lệnh thực thi nếu biểu_thức === giá_trị_1
        break;
    case giá_trị_2:
        // Khối lệnh thực thi nếu biểu_thức === giá_trị_2
        break;
    // ...các case khác...
    default:
        // Khối lệnh thực thi nếu không có case nào khớp
}
```

### **Ví dụ:**
```javascript
let fruit = "apple";
switch (fruit) {
    case "banana":
        console.log("This is a banana.");
        break;
    case "apple":
        console.log("This is an apple.");
        break;
    default:
        console.log("Unknown fruit.");
}
```

## 4. `break` và `continue` trong vòng lặp
### **`break` - Dừng vòng lặp:**
Câu lệnh `break` dùng để dừng vòng lặp ngay lập tức.

### **Ví dụ:**
```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }
    console.log(i);
}
// Output: 0 1 2 3 4
```

### **`continue` - Bỏ qua một lần lặp:**
Câu lệnh `continue` dùng để bỏ qua lần lặp hiện tại và tiếp tục với lần lặp tiếp theo.

### **Ví dụ:**
```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        continue;
    }
    console.log(i);
}
// Output: 0 1 2 3 4 6 7 8 9
```

## **Kết luận**
Bài viết này đã cung cấp những kiến thức cơ bản về cấu trúc điều kiện, vòng lặp, và các cấu trúc điều khiển khác trong JavaScript. Đây là những khái niệm nền tảng quan trọng giúp bạn xây dựng các ứng dụng web hiệu quả.