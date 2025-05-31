# CONTEXT VÀ GUIDELINE CHO SERIES TÀI LIỆU JAVASCRIPT

## 🎯 Mục tiêu tổng thể

Tạo ra một bộ tài liệu JavaScript **hoàn chỉnh, dễ hiểu, thực tế** dành cho học sinh cấp 3 Việt Nam, giúp các em:

-   Nắm vững kiến thức nền tảng JavaScript
-   Áp dụng được vào thực tế qua các ví dụ gần gũi
-   Có tài liệu tham khảo đầy đủ khi cần

---

## 📚 Cấu trúc tổng thể series

```
JS-Document/
├── Kiến thức nền tảng/
│   ├── Variables/           # Biến và kiểu dữ liệu
│   ├── Operators/           # Toán tử
│   ├── Conditionals/        # Câu lệnh điều kiện
│   ├── Loops/              # Vòng lặp
│   ├── Functions/          # Hàm
│   ├── Array/              # Mảng ✅
│   ├── Objects/            # Đối tượng
│   ├── Strings/            # Chuỗi
│   ├── Numbers/            # Số
│   └── DOM/                # Thao tác DOM cơ bản
├── Nâng cao/
│   ├── ES6+/               # Cú pháp mới
│   ├── Async/              # Bất đồng bộ
│   ├── Modules/            # Module
│   └── APIs/               # Làm việc với API
└── Dự án thực tế/
    ├── Calculator/         # Máy tính
    ├── Todo-App/          # Quản lý công việc
    └── Mini-Games/        # Game nhỏ
```

---

## 🎨 Template chuẩn cho mỗi file README.md

### 1. Header và mục lục

```markdown
# [TÊN CHỦ ĐỀ] TRONG JAVASCRIPT

## MỤC LỤC

1. [Khái niệm cơ bản](#1-khái-niệm-cơ-bản)
2. [Tại sao cần học](#2-tại-sao-cần-học)
3. [Cú pháp cơ bản](#3-cú-pháp-cơ-bản)
4. [Ví dụ thực tế](#4-ví-dụ-thực-tế)
5. [Phương thức/Thuộc tính](#5-phương-thức-thuộc-tính)
6. [Bài tập thực hành](#6-bài-tập-thực-hành)
7. [Tham khảo đầy đủ](#7-tham-khảo-đầy-đủ)
8. [Tóm tắt](#8-tóm-tắt)
```

### 2. Nội dung từng phần

**Phần 1: Khái niệm cơ bản**

-   Định nghĩa ngắn gọn, dễ hiểu
-   So sánh với thứ quen thuộc trong đời sống
-   Code example đơn giản nhất

**Phần 2: Tại sao cần học**

-   Lợi ích thực tế
-   Ví dụ ứng dụng trong cuộc sống
-   So sánh cách làm cũ vs mới

**Phần 3-4: Cú pháp và ví dụ**

-   Từ đơn giản đến phức tạp
-   Ví dụ gần gũi với học sinh (điểm số, danh sách lớp, etc.)
-   Comment tiếng Việt trong code

**Phần 5: Phương thức/Thuộc tính**

-   Bảng tham khảo đầy đủ
-   Phân cấp độ khó (cấp 3 / nâng cao)
-   Ví dụ cụ thể cho từng phương thức

**Phần 6: Bài tập**

-   3-5 bài tập từ dễ đến khó
-   Có gợi ý và đáp án
-   Tập trung vào ứng dụng thực tế

---

## 🗣️ Ngôn ngữ và phong cách viết

### Nguyên tắc cơ bản:

-   **100% tiếng Việt**, trừ thuật ngữ kỹ thuật không dịch được
-   **Thân thiện, gần gũi** như anh/chị trong gia đình
-   **Nghiêm túc nhưng không khô khan**

### Thuật ngữ chuẩn:

| English        | Tiếng Việt         | Ghi chú |
| -------------- | ------------------ | ------- |
| Array          | Mảng               |         |
| Function       | Hàm                |         |
| Variable       | Biến               |         |
| Object         | Đối tượng          |         |
| Method         | Phương thức        |         |
| Property       | Thuộc tính         |         |
| Index          | Chỉ số/Vị trí      |         |
| Loop           | Vòng lặp           |         |
| Condition      | Điều kiện          |         |
| String         | Chuỗi              |         |
| Number         | Số                 |         |
| Boolean        | Logic (true/false) |         |
| null/undefined | Giá trị rỗng       |         |

### Cách gọi người đọc:

-   **"Các em"** khi nói chung
-   **"Em"** khi hướng dẫn cụ thể
-   **"Chúng ta"** khi cùng thực hiện
-   Tránh "bạn", "các bạn" (không phù hợp với lứa tuổi)

---

## 💡 Ví dụ và bài tập chuẩn

### Chủ đề ví dụ ưu tiên:

1. **Quản lý điểm số** (toán, lý, hóa, văn...)
2. **Danh sách lớp học** (tên học sinh, sĩ số...)
3. **Thời khóa biểu** (môn học, giáo viên...)
4. **Quản lý sách** (thư viện, sách giáo khoa...)
5. **Hoạt động ngoại khóa** (câu lạc bộ, đội nhóm...)
6. **Mua sắm** (danh sách đồ dùng học tập...)

### Tên biến chuẩn:

```javascript
// Tên người
const hocSinh = ['An', 'Bình', 'Chi', 'Dung'];
const giaoVien = ['Cô Lan', 'Thầy Nam'];

// Điểm số
const diemToan = [8, 9, 7, 10, 6];
const diemTrungBinh = 8.2;

// Môn học
const monHoc = ['Toán', 'Lý', 'Hóa', 'Văn', 'Anh'];

// Thời gian
const ngayHoc = ['Thứ 2', 'Thứ 3', 'Thứ 4'];

// Đồ vật
const doDungHocTap = ['Bút', 'Tập', 'Thước', 'Máy tính'];
```

---

## 📊 Format bảng và code

### Bảng tham khảo:

```markdown
| Phương thức | Chức năng      | Ví dụ          |
| ----------- | -------------- | -------------- |
| `method()`  | Mô tả ngắn gọn | `arr.method()` |
```

### Code blocks:

```javascript
// Comment tiếng Việt mô tả
const mang = [1, 2, 3];

// Giải thích từng bước
for (let i = 0; i < mang.length; i++) {
	console.log('Phần tử thứ ' + (i + 1) + ': ' + mang[i]);
}
```

### Kết quả mong đợi:

```javascript
console.log(ketQua); // [1, 2, 3, 4]
```

---

## 🎯 Level phân cấp kiến thức

### Cơ bản:

-   Cú pháp đơn giản, dễ hiểu
-   Ví dụ thực tế gần gũi
-   Focus vào sử dụng, ít lý thuyết sâu
-   70% nội dung tập trung ở đây

### Nâng cao:

-   Cú pháp ES6+
-   Khái niệm sâu hơn
-   Bài tập phức tạp
-   20% nội dung

### Chuyên sâu:

-   Advanced concepts
-   Performance optimization
-   Best practices
-   10% nội dung (chỉ đề cập)

---

## 🚫 Tránh những điều này

### Về ngôn ngữ:

-   ❌ Thuật ngữ tiếng Anh không cần thiết
-   ❌ Ngôn ngữ quá học thuật
-   ❌ Giải thích dài dòng, rối rắm
-   ❌ Ví dụ xa lạ, không thực tế

### Về code:

-   ❌ Code phức tạp ngay từ đầu
-   ❌ Không có comment tiếng Việt
-   ❌ Ví dụ không liên quan đến học sinh
-   ❌ Thiếu giải thích output

### Về cấu trúc:

-   ❌ Mục lục không rõ ràng
-   ❌ Thiếu bài tập thực hành
-   ❌ Không có phần tham khảo
-   ❌ Bỏ qua phần tóm tắt

---

## ✅ Checklist hoàn thành một bài

### Nội dung:

-   [ ] Mục lục đầy đủ với anchor links
-   [ ] Từng phần có ít nhất 1 ví dụ code
-   [ ] Ví dụ gần gũi với học sinh cấp 3
-   [ ] 3-5 bài tập thực hành có độ khó tăng dần
-   [ ] Bảng tham khảo đầy đủ methods/properties
-   [ ] Phần tóm tắt ngắn gọn

### Định dạng:

-   [ ] Code có comment tiếng Việt
-   [ ] Bảng format đúng chuẩn
-   [ ] Headers phân cấp rõ ràng
-   [ ] Emoji phù hợp để tăng thẩm mỹ

### Chất lượng:

-   [ ] Ngôn ngữ phù hợp với cấp 3
-   [ ] Không có lỗi chính tả
-   [ ] Code chạy được, không có bug
-   [ ] Ví dụ thực tế, có ý nghĩa

---

## 🎨 Style guide cho emoji

| Loại nội dung      | Emoji | Sử dụng               |
| ------------------ | ----- | --------------------- |
| Phương thức cơ bản | 📋    | Bảng methods chính    |
| Tìm kiếm           | 🔍    | Search methods        |
| Cắt/nối            | ✂️    | Splice, slice, concat |
| Vòng lặp           | 🔄    | Iteration methods     |
| Mới/Nâng cao       | 🆕    | ES6+ features         |
| Mẹo                | 💡    | Tips and tricks       |
| Bài tập            | 🎯    | Exercises             |
| Kết luận           | 📚    | Summary section       |
| Cảnh báo           | ⚠️    | Important notes       |
| Thành công         | ✅    | Correct examples      |
| Lỗi                | ❌    | Wrong examples        |

---

## 💼 Template snippet cho copy-paste

````markdown
## [SỐ]. [TÊN PHẦN]

### [Tiểu mục nếu cần]

**Giải thích ngắn gọn về tính năng**

```javascript
// Ví dụ đơn giản
const [tenBien] = ['dữ liệu', 'mẫu'];

// Giải thích code
console.log([tenBien]); // Kết quả mong đợi
```
````

**Lưu ý quan trọng:** [Điều cần nhớ]

---

```

**Nhớ:** Mỗi bài viết phải như một cuốn sách nhỏ - đầy đủ, dễ hiểu, và có thể đọc độc lập!
```
