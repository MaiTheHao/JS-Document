# MẢNG TRONG JAVASCRIPT (ARRAYS)

## MỤC LỤC

1. [Mảng là gì?](#1-mảng-là-gì)
2. [Tại sao sử dụng mảng?](#2-tại-sao-sử-dụng-mảng)
3. [Cách tạo mảng](#3-cách-tạo-mảng)
4. [Truy cập phần tử trong mảng](#4-truy-cập-phần-tử-trong-mảng)
5. [Thay đổi phần tử trong mảng](#5-thay-đổi-phần-tử-trong-mảng)
6. [Thuộc tính và phương thức cơ bản](#6-thuộc-tính-và-phương-thức-cơ-bản)
7. [Duyệt mảng](#7-duyệt-mảng)
8. [Thêm và xóa phần tử](#8-thêm-và-xóa-phần-tử)
9. [Tìm kiếm trong mảng](#9-tìm-kiếm-trong-mảng)
10. [Sắp xếp mảng](#10-sắp-xếp-mảng)
11. [Bài tập thực hành](#11-bài-tập-thực-hành)
12. [Tham khảo đầy đủ các phương thức Array](#12-tham-khảo-đầy-đủ-các-phương-thức-array)

---

## 1. Mảng là gì?

**Mảng** là một biến đặc biệt có thể lưu trữ nhiều giá trị cùng một lúc.

```javascript
const diemSo = [8, 9, 7, 10, 6];
```

Thay vì khai báo nhiều biến riêng lẻ:

```javascript
let diem1 = 8;
let diem2 = 9;
let diem3 = 7;
// ... rất bất tiện!
```

---

## 2. Tại sao sử dụng mảng?

-   **Tiết kiệm code**: Lưu trữ nhiều dữ liệu trong một biến
-   **Dễ quản lý**: Có thể duyệt qua tất cả phần tử một cách dễ dàng
-   **Linh hoạt**: Có thể thêm, sửa, xóa phần tử

**Ví dụ thực tế:**

```javascript
const lop10A = ['Minh', 'Lan', 'Hùng', 'Mai', 'Đức'];
const diemToan = [8, 9, 7, 10, 6];
```

---

## 3. Cách tạo mảng

### Cách 1: Sử dụng dấu ngoặc vuông (Khuyến khích)

```javascript
const hocSinh = ['An', 'Bình', 'Chi'];
const diemSo = [8, 9, 7, 10];
const mangRong = [];
```

### Cách 2: Tạo mảng rỗng rồi thêm phần tử

```javascript
const monHoc = [];
monHoc[0] = 'Toán';
monHoc[1] = 'Lý';
monHoc[2] = 'Hóa';
```

### Cách 3: Sử dụng từ khóa new (Ít dùng)

```javascript
const hocSinh = new Array('An', 'Bình', 'Chi');
```

---

## 4. Truy cập phần tử trong mảng

Mảng sử dụng **chỉ số** (index) để truy cập phần tử, bắt đầu từ **0**.

```javascript
const hocSinh = ['An', 'Bình', 'Chi', 'Dung'];

console.log(hocSinh[0]); // "An" - phần tử đầu tiên
console.log(hocSinh[1]); // "Bình" - phần tử thứ hai
console.log(hocSinh[3]); // "Dung" - phần tử thứ tư
```

**Lưu ý quan trọng:** Chỉ số bắt đầu từ 0, không phải 1!

---

## 5. Thay đổi phần tử trong mảng

```javascript
const diemSo = [8, 7, 9];
diemSo[1] = 10; // Thay đổi điểm thứ 2 từ 7 thành 10

console.log(diemSo); // [8, 10, 9]
```

---

## 6. Thuộc tính và phương thức cơ bản

### Thuộc tính length (độ dài)

```javascript
const hocSinh = ['An', 'Bình', 'Chi'];
console.log(hocSinh.length); // 3
```

### Phương thức toString() (chuyển thành chuỗi)

```javascript
const traicay = ['Táo', 'Cam', 'Chuối'];
console.log(traicay.toString()); // "Táo,Cam,Chuối"
```

---

## 7. Duyệt mảng

### Cách 1: Sử dụng vòng lặp for

```javascript
const diemSo = [8, 9, 7, 10, 6];

for (let i = 0; i < diemSo.length; i++) {
	console.log('Điểm thứ ' + (i + 1) + ': ' + diemSo[i]);
}
```

### Cách 2: Sử dụng forEach (dễ hiểu hơn)

```javascript
const hocSinh = ['An', 'Bình', 'Chi'];

hocSinh.forEach(function (ten, viTri) {
	console.log('Học sinh thứ ' + (viTri + 1) + ': ' + ten);
});
```

---

## 8. Thêm và xóa phần tử

### Thêm phần tử

**push()** - Thêm vào cuối mảng:

```javascript
const hocSinh = ['An', 'Bình'];
hocSinh.push('Chi'); // Thêm "Chi" vào cuối
console.log(hocSinh); // ["An", "Bình", "Chi"]
```

**unshift()** - Thêm vào đầu mảng:

```javascript
const hocSinh = ['Bình', 'Chi'];
hocSinh.unshift('An'); // Thêm "An" vào đầu
console.log(hocSinh); // ["An", "Bình", "Chi"]
```

### Xóa phần tử

**pop()** - Xóa phần tử cuối:

```javascript
const hocSinh = ['An', 'Bình', 'Chi'];
let phanTuCuoi = hocSinh.pop(); // Xóa và trả về "Chi"
console.log(hocSinh); // ["An", "Bình"]
```

**shift()** - Xóa phần tử đầu:

```javascript
const hocSinh = ['An', 'Bình', 'Chi'];
let phanTuDau = hocSinh.shift(); // Xóa và trả về "An"
console.log(hocSinh); // ["Bình", "Chi"]
```

---

## 9. Tìm kiếm trong mảng

### indexOf() - Tìm vị trí của phần tử

```javascript
const hocSinh = ['An', 'Bình', 'Chi', 'An'];
console.log(hocSinh.indexOf('Bình')); // 1
console.log(hocSinh.indexOf('Dung')); // -1 (không tìm thấy)
```

### includes() - Kiểm tra có tồn tại không

```javascript
const monHoc = ['Toán', 'Lý', 'Hóa'];
console.log(monHoc.includes('Toán')); // true
console.log(monHoc.includes('Anh')); // false
```

---

## 10. Sắp xếp mảng

### sort() - Sắp xếp theo thứ tự alphabet

```javascript
const hocSinh = ['Chi', 'An', 'Bình'];
hocSinh.sort();
console.log(hocSinh); // ["An", "Bình", "Chi"]
```

### Sắp xếp số

```javascript
const diemSo = [8, 10, 6, 9, 7];

// Sắp xếp tăng dần
diemSo.sort(function (a, b) {
	return a - b;
});
console.log(diemSo); // [6, 7, 8, 9, 10]

// Sắp xếp giảm dần
diemSo.sort(function (a, b) {
	return b - a;
});
console.log(diemSo); // [10, 9, 8, 7, 6]
```

---

## 11. Bài tập thực hành

### Bài 1: Quản lý điểm số

```javascript
// Tạo mảng điểm của 5 học sinh
const diemToan = [8, 9, 7, 6, 10];

// 1. In ra tất cả điểm số
// 2. Tính điểm trung bình
// 3. Tìm điểm cao nhất và thấp nhất
// 4. Đếm số học sinh có điểm >= 8
```

### Bài 2: Danh sách mua sắm

```javascript
// Tạo danh sách mua sắm
const danhSachMuaSam = ['Sữa', 'Bánh mì', 'Trứng'];

// 1. Thêm "Gạo" vào cuối danh sách
// 2. Thêm "Rau" vào đầu danh sách
// 3. Xóa món cuối cùng
// 4. Kiểm tra có "Sữa" trong danh sách không
```

### Bài 3: Lọc dữ liệu

```javascript
// Cho mảng điểm số
const diemSo = [5, 8, 6, 9, 4, 7, 10, 3];

// Tạo mảng mới chỉ chứa những điểm >= 7
const diemKha = [];
for (let i = 0; i < diemSo.length; i++) {
	if (diemSo[i] >= 7) {
		diemKha.push(diemSo[i]);
	}
}
console.log(diemKha); // [8, 9, 7, 10]
```

---

## Tóm tắt

-   **Mảng** giúp lưu trữ nhiều giá trị trong một biến
-   **Chỉ số** bắt đầu từ 0
-   Sử dụng **push/pop** để thêm/xóa cuối mảng
-   Sử dụng **unshift/shift** để thêm/xóa đầu mảng
-   **length** cho biết độ dài mảng
-   **indexOf/includes** để tìm kiếm
-   **sort()** để sắp xếp

**Lưu ý:** Hãy luyện tập thường xuyên với các bài tập để thành thạo mảng!

---

## 12. Tham khảo đầy đủ các phương thức Array

### 📋 Phương thức cơ bản (Dành cho cấp 3)

| Phương thức  | Chức năng             | Ví dụ                |
| ------------ | --------------------- | -------------------- |
| `push()`     | Thêm phần tử vào cuối | `arr.push("mới")`    |
| `pop()`      | Xóa phần tử cuối      | `arr.pop()`          |
| `unshift()`  | Thêm phần tử vào đầu  | `arr.unshift("đầu")` |
| `shift()`    | Xóa phần tử đầu       | `arr.shift()`        |
| `length`     | Độ dài mảng           | `arr.length`         |
| `indexOf()`  | Tìm vị trí phần tử    | `arr.indexOf("tìm")` |
| `includes()` | Kiểm tra có tồn tại   | `arr.includes("có")` |
| `sort()`     | Sắp xếp mảng          | `arr.sort()`         |
| `reverse()`  | Đảo ngược mảng        | `arr.reverse()`      |
| `join()`     | Nối thành chuỗi       | `arr.join("-")`      |
| `toString()` | Chuyển thành chuỗi    | `arr.toString()`     |

### 🔍 Phương thức tìm kiếm

| Phương thức           | Chức năng                           | Trả về                 | Ví dụ                       |
| --------------------- | ----------------------------------- | ---------------------- | --------------------------- |
| `indexOf(item)`       | Tìm vị trí đầu tiên                 | Số hoặc -1             | `arr.indexOf("An")`         |
| `lastIndexOf(item)`   | Tìm vị trí cuối cùng                | Số hoặc -1             | `arr.lastIndexOf("An")`     |
| `includes(item)`      | Kiểm tra có tồn tại                 | true/false             | `arr.includes("Bình")`      |
| `find(function)`      | Tìm phần tử đầu tiên thỏa điều kiện | Phần tử hoặc undefined | `arr.find(x => x > 8)`      |
| `findIndex(function)` | Tìm vị trí đầu tiên thỏa điều kiện  | Số hoặc -1             | `arr.findIndex(x => x > 8)` |

### ✂️ Phương thức cắt và nối

| Phương thức                      | Chức năng    | Thay đổi mảng gốc? | Ví dụ                     |
| -------------------------------- | ------------ | ------------------ | ------------------------- |
| `slice(start, end)`              | Cắt một phần | Không              | `arr.slice(1, 3)`         |
| `splice(start, count, ...items)` | Xóa và thêm  | Có                 | `arr.splice(1, 2, "mới")` |
| `concat(arr2)`                   | Nối hai mảng | Không              | `arr1.concat(arr2)`       |

### 🔄 Phương thức lặp (Nâng cao - Lớp 11, 12)

| Phương thức         | Chức năng                              | Trả về      | Ví dụ                                    |
| ------------------- | -------------------------------------- | ----------- | ---------------------------------------- |
| `forEach(function)` | Duyệt từng phần tử                     | undefined   | `arr.forEach(item => console.log(item))` |
| `map(function)`     | Tạo mảng mới sau khi biến đổi          | Mảng mới    | `arr.map(x => x * 2)`                    |
| `filter(function)`  | Lọc phần tử thỏa điều kiện             | Mảng mới    | `arr.filter(x => x > 5)`                 |
| `reduce(function)`  | Gộp thành một giá trị                  | Một giá trị | `arr.reduce((sum, x) => sum + x, 0)`     |
| `every(function)`   | Kiểm tra tất cả thỏa điều kiện         | true/false  | `arr.every(x => x > 0)`                  |
| `some(function)`    | Kiểm tra có ít nhất một thỏa điều kiện | true/false  | `arr.some(x => x > 8)`                   |

### 📊 Phương thức sắp xếp

```javascript
// Sắp xếp chuỗi
const ten = ['Chi', 'An', 'Bình'];
ten.sort(); // ["An", "Bình", "Chi"]

// Sắp xếp số tăng dần
const diem = [8, 10, 6, 9];
diem.sort((a, b) => a - b); // [6, 8, 9, 10]

// Sắp xếp số giảm dần
diem.sort((a, b) => b - a); // [10, 9, 8, 6]

// Đảo ngược
diem.reverse(); // Đảo ngược thứ tự hiện tại
```

### 🆕 Phương thức mới (ES6+)

| Phương thức       | Chức năng               | Ví dụ                    |
| ----------------- | ----------------------- | ------------------------ |
| `Array.from()`    | Tạo mảng từ object khác | `Array.from("ABC")`      |
| `Array.isArray()` | Kiểm tra có phải mảng   | `Array.isArray([1,2,3])` |
| `fill(value)`     | Điền giá trị            | `arr.fill(0)`            |
| `flat()`          | Làm phẳng mảng lồng     | `[[1,2],[3,4]].flat()`   |

### 💡 Mẹo nhớ nhanh

**Thêm/Xóa:**

-   **P**ush = **P**hía sau (cuối)
-   **P**op = **P**hía sau (cuối)
-   **U**nshift = **U**p front (đầu)
-   **S**hift = **S**tart (đầu)

**Tìm kiếm:**

-   `indexOf` = tìm **vị trí**
-   `includes` = có **tồn tại** không?
-   `find` = tìm **phần tử**

**Nhớ index:**

-   Mảng bắt đầu từ **0**
-   `length` luôn lớn hơn index cuối cùng 1 đơn vị

### 🎯 Bài tập tổng hợp

```javascript
// Cho mảng điểm số của lớp
const diemLop = [8, 6, 9, 7, 10, 5, 8, 9, 6, 7];

// Thực hiện các yêu cầu sau:
console.log('1. Số học sinh:', diemLop.length);
console.log('2. Điểm cao nhất:', Math.max(...diemLop));
console.log('3. Điểm thấp nhất:', Math.min(...diemLop));
console.log('4. Học sinh giỏi (>= 8):', diemLop.filter((d) => d >= 8).length);
console.log('5. Điểm trung bình:', diemLop.reduce((sum, d) => sum + d) / diemLop.length);
console.log(
	'6. Sắp xếp tăng dần:',
	[...diemLop].sort((a, b) => a - b)
);
```

---

## 📚 Kết luận

Mảng là công cụ cực kỳ mạnh mẽ trong JavaScript! Với các em cấp 3:

-   **Tập trung vào:** push, pop, length, indexOf, includes, sort
-   **Luyện tập:** Làm nhiều bài tập về quản lý danh sách
-   **Nâng cao:** Khi lên lớp 11-12 sẽ học thêm map, filter, reduce

**Tip cuối:** Code nhiều vào, đừng chỉ đọc lý thuyết. Array như học đi xe máy vậy, phải thực hành mới thuần thục được!
