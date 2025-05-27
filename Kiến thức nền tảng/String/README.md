# CHUỖI TRONG JAVASCRIPT (STRINGS)

## MỤC LỤC

1. [Chuỗi là gì?](#1-chuỗi-là-gì)
2. [Tại sao cần học chuỗi?](#2-tại-sao-cần-học-chuỗi)
3. [Cách tạo chuỗi](#3-cách-tạo-chuỗi)
4. [Truy cập ký tự trong chuỗi](#4-truy-cập-ký-tự-trong-chuỗi)
5. [Phương thức cơ bản](#5-phương-thức-cơ-bản)
6. [Cắt và nối chuỗi](#6-cắt-và-nối-chuỗi)
7. [Tìm kiếm trong chuỗi](#7-tìm-kiếm-trong-chuỗi)
8. [Chuyển đổi định dạng](#8-chuyển-đổi-định-dạng)
9. [Template Strings (Nâng cao)](#9-template-strings-nâng-cao)
10. [Bài tập thực hành](#10-bài-tập-thực-hành)
11. [Tham khảo đầy đủ](#11-tham-khảo-đầy-đủ)
12. [Tóm tắt](#12-tóm-tắt)

---

## 1. Chuỗi là gì?

**Chuỗi** (String) là kiểu dữ liệu dùng để lưu trữ văn bản - tức là những ký tự, từ ngữ, câu văn.

```javascript
const tenHocSinh = 'Nguyễn Văn An';
const monHoc = 'Toán học';
const thongBao = 'Chúc mừng em đã đạt điểm 10!';
```

Chuỗi giống như một dãy ký tự được **xếp thành hàng**, mỗi ký tự có vị trí riêng.

---

## 2. Tại sao cần học chuỗi?

-   **Hiển thị thông tin**: Tên học sinh, thông báo điểm số
-   **Xử lý dữ liệu**: Kiểm tra email, số điện thoại
-   **Tương tác người dùng**: Nhập liệu, tìm kiếm
-   **Tạo nội dung**: Tạo báo cáo, thông báo tự động

**Ví dụ thực tế:**

```javascript
const tenHocSinh = 'Trần Thị Lan';
const diem = 8.5;
const thongBao = 'Em ' + tenHocSinh + ' đạt điểm ' + diem + ' môn Toán';
console.log(thongBao); // "Em Trần Thị Lan đạt điểm 8.5 môn Toán"
```

---

## 3. Cách tạo chuỗi

### Cách 1: Dùng dấu ngoặc kép (khuyến khích)

```javascript
const hoTen = 'Nguyễn Văn An';
const lop = '10A1';
```

### Cách 2: Dùng dấu ngoặc đơn

```javascript
const monHoc = 'Toán học';
const phong = 'A101';
```

### Cách 3: Dùng dấu backtick (nâng cao)

```javascript
const tenTruong = `THPT Nguyễn Du`;
const diaChi = `123 Đường ABC, Quận 1`;
```

### Cách 4: Dùng từ khóa new (ít dùng)

```javascript
const chuoi = new String('Xin chào');
```

### 💡 Lưu ý về dấu ngoặc trong chuỗi

```javascript
// Đúng - dùng dấu khác nhau
const cauNoi = "Hôm nay trời 'đẹp' quá!";
const thongBao = 'Cô giáo nói: "Các em làm bài tập về nhà"';

// Sai - dùng cùng loại dấu
// const loi = "Cô nói: "Làm bài tập""; // ❌ Lỗi!
```

---

## 4. Truy cập ký tự trong chuỗi

### Thuộc tính length (độ dài)

```javascript
const tenHocSinh = 'Nguyễn Văn An';
console.log(tenHocSinh.length); // 13 ký tự (kể cả dấu cách)
```

### Truy cập ký tự theo vị trí

```javascript
const ten = 'Lan';
console.log(ten[0]); // "L" - ký tự đầu tiên
console.log(ten[1]); // "a" - ký tự thứ hai
console.log(ten[2]); // "n" - ký tự cuối cùng

// Ký tự cuối cùng
console.log(ten[ten.length - 1]); // "n"
```

**Lưu ý quan trọng:** Vị trí bắt đầu từ 0, không phải 1!

---

## 5. Phương thức cơ bản

### charAt() - Lấy ký tự tại vị trí

```javascript
const hoTen = 'Nguyễn An';
console.log(hoTen.charAt(0)); // "N"
console.log(hoTen.charAt(7)); // "A"
```

### indexOf() - Tìm vị trí ký tự/chuỗi

```javascript
const email = 'an.nguyen@gmail.com';
console.log(email.indexOf('@')); // 10
console.log(email.indexOf('xyz')); // -1 (không tìm thấy)
```

### includes() - Kiểm tra có chứa không

```javascript
const tenLop = '10A1 Toán Tin';
console.log(tenLop.includes('Toán')); // true
console.log(tenLop.includes('Hóa')); // false
```

### toString() - Chuyển thành chuỗi

```javascript
const diem = 8.5;
const chuoiDiem = diem.toString();
console.log(chuoiDiem); // "8.5"
console.log(typeof chuoiDiem); // "string"
```

---

## 6. Cắt và nối chuỗi

### slice() - Cắt một phần chuỗi

```javascript
const hoTenDayDu = 'Nguyễn Văn An';

// Cắt từ vị trí 7 đến hết
const ten = hoTenDayDu.slice(7); // "Văn An"

// Cắt từ vị trí 0 đến 6 (không bao gồm vị trí 7)
const ho = hoTenDayDu.slice(0, 7); // "Nguyễn "

// Cắt từ cuối lên (-2 nghĩa là 2 ký tự cuối)
const cuoi = hoTenDayDu.slice(-2); // "An"
```

### substring() - Cắt chuỗi (tương tự slice)

```javascript
const lop = '10A1-KHTN';
const khoi = lop.substring(0, 2); // "10"
const ban = lop.substring(3); // "1-KHTN"
```

### concat() - Nối chuỗi

```javascript
const ho = 'Nguyễn';
const ten = 'An';
const hoTen = ho.concat(' ', ten);
console.log(hoTen); // "Nguyễn An"

// Cách dễ hiểu hơn - dùng dấu +
const hoTen2 = ho + ' ' + ten; // "Nguyễn An"
```

### split() - Tách chuỗi thành mảng

```javascript
const danhSach = 'An,Bình,Chi,Dung';
const mangHocSinh = danhSach.split(',');
console.log(mangHocSinh); // ["An", "Bình", "Chi", "Dung"]

// Tách từng ký tự
const ten = 'Lan';
const kyTu = ten.split('');
console.log(kyTu); // ["L", "a", "n"]
```

---

## 7. Tìm kiếm trong chuỗi

### indexOf() và lastIndexOf()

```javascript
const cauVan = 'Toán là môn Toán rất hay';

console.log(cauVan.indexOf('Toán')); // 0 (vị trí đầu tiên)
console.log(cauVan.lastIndexOf('Toán')); // 12 (vị trí cuối cùng)
```

### search() - Tìm kiếm nâng cao

```javascript
const soDienThoai = 'Liên hệ: 0123456789';
const viTri = soDienThoai.search('0123'); // 9
```

### startsWith() và endsWith()

```javascript
const email = 'hocsinh@school.edu.vn';

console.log(email.startsWith('hocsinh')); // true
console.log(email.endsWith('.vn')); // true
console.log(email.startsWith('giaovien')); // false
```

### match() - Tìm tất cả kết quả khớp

```javascript
const vanBan = 'Điểm Toán: 8, Điểm Lý: 9, Điểm Hóa: 7';
const ketQua = vanBan.match(/\d+/g); // Tìm tất cả số
console.log(ketQua); // ["8", "9", "7"]
```

---

## 8. Chuyển đổi định dạng

### toUpperCase() và toLowerCase()

```javascript
const ten = 'Nguyễn Văn An';
console.log(ten.toUpperCase()); // "NGUYỄN VĂN AN"
console.log(ten.toLowerCase()); // "nguyễn văn an"

// Ứng dụng: Chuẩn hóa dữ liệu
const nhapLieu = '   NgUyEn VaN aN   ';
const chuanHoa = nhapLieu.trim().toLowerCase();
console.log(chuanHoa); // "nguyen van an"
```

### trim() - Xóa khoảng trắng thừa

```javascript
const nhapLieu = '   Nguyễn Văn An   ';
console.log(nhapLieu.trim()); // "Nguyễn Văn An"

// Chỉ xóa đầu hoặc cuối
console.log(nhapLieu.trimStart()); // "Nguyễn Văn An   "
console.log(nhapLieu.trimEnd()); // "   Nguyễn Văn An"
```

### replace() - Thay thế

```javascript
const thongBao = 'Chúc mừng em An đạt điểm cao!';
const thongBaoMoi = thongBao.replace('An', 'Lan');
console.log(thongBaoMoi); // "Chúc mừng em Lan đạt điểm cao!";

// Thay thế tất cả
const vanBan = 'Toán rất hay, Toán rất thú vị';
const moi = vanBan.replace(/Toán/g, 'Lý');
console.log(moi); // "Lý rất hay, Lý rất thú vị"
```

### repeat() - Lặp lại chuỗi

```javascript
const dau = '*';
const duongKe = dau.repeat(20);
console.log(duongKe); // "********************"

const kyTu = 'Xa ';
const nhacLai = kyTu.repeat(3);
console.log(nhacLai); // "Xa Xa Xa "
```

---

## 9. Template Strings (Nâng cao)

### Cú pháp cơ bản với backtick

```javascript
const ten = 'Lan';
const diem = 9;

// Cách cũ - khó đọc
const thongBao1 = 'Em ' + ten + ' đạt điểm ' + diem + ' môn Toán';

// Cách mới - dễ đọc
const thongBao2 = `Em ${ten} đạt điểm ${diem} môn Toán`;
console.log(thongBao2); // "Em Lan đạt điểm 9 môn Toán"
```

### Chuỗi nhiều dòng

```javascript
const thongBao = `
Kết quả học tập:
- Toán: 9 điểm
- Lý: 8 điểm  
- Hóa: 8.5 điểm
Chúc mừng em!
`;
console.log(thongBao);
```

### Biểu thức trong Template String

```javascript
const diem1 = 8;
const diem2 = 9;
const diem3 = 7;

const ketQua = `Điểm trung bình: ${(diem1 + diem2 + diem3) / 3}`;
console.log(ketQua); // "Điểm trung bình: 8"

const trangThai = `Kết quả: ${diem1 >= 8 ? 'Đạt' : 'Không đạt'}`;
console.log(trangThai); // "Kết quả: Đạt"
```

---

## 10. Bài tập thực hành

### Bài 1: Xử lý thông tin học sinh

```javascript
const hoTenDayDu = '  nguyễn văn an  ';

// Yêu cầu:
// 1. Loại bỏ khoảng trắng thừa
// 2. Viết hoa chữ cái đầu mỗi từ
// 3. Tách họ và tên

// Đáp án:
const sach = hoTenDayDu.trim(); // "nguyễn văn an"
const vietHoa = sach.charAt(0).toUpperCase() + sach.slice(1); // "Nguyễn văn an"
const mangTu = sach.split(' '); // ["nguyễn", "văn", "an"]
```

### Bài 2: Kiểm tra email hợp lệ

```javascript
const email = 'hocsinh@school.edu.vn';

// Kiểm tra:
// 1. Có chứa dấu @ không?
// 2. Có kết thúc bằng .edu.vn không?
// 3. Phần trước @ có ít nhất 3 ký tự không?

console.log(email.includes('@')); // true
console.log(email.endsWith('.edu.vn')); // true
console.log(email.indexOf('@') >= 3); // true
```

### Bài 3: Tạo mã học sinh

```javascript
const ho = 'Nguyễn';
const ten = 'An';
const namSinh = 2005;
const lop = '10A1';

// Tạo mã: NA05A1 (2 ký tự đầu họ + tên + 2 số cuối năm sinh + lớp)
const ma = ho.charAt(0) + ten.charAt(0) + namSinh.toString().slice(-2) + lop;
console.log(ma); // "NA0510A1"
```

### Bài 4: Đếm từ trong văn bản

```javascript
const vanBan = 'JavaScript là ngôn ngữ lập trình phổ biến';

// Đếm số từ
const soTu = vanBan.split(' ').length;
console.log(`Văn bản có ${soTu} từ`); // "Văn bản có 7 từ"

// Đếm ký tự (không kể dấu cách)
const soKyTu = vanBan.replace(/ /g, '').length;
console.log(`Có ${soKyTu} ký tự`);
```

### Bài 5: Tạo báo cáo điểm

```javascript
const danhSachDiem = 'Toán:8,Lý:9,Hóa:7,Văn:8.5';

// Chuyển thành định dạng đẹp
const mangMon = danhSachDiem.split(',');
let baoCao = '=== BÁO CÁO ĐIỂM ===\n';

for (let mon of mangMon) {
	const [tenMon, diem] = mon.split(':');
	baoCao += `${tenMon}: ${diem} điểm\n`;
}

console.log(baoCao);
// === BÁO CÁO ĐIỂM ===
// Toán: 8 điểm
// Lý: 9 điểm
// Hóa: 7 điểm
// Văn: 8.5 điểm
```

### Bài 6: Chuẩn hóa tên học sinh

```javascript
const danhSachLop = 'nguyễn văn an, trần THỊ lan,  lê minh   HÙNG  ';

// Yêu cầu: Chuẩn hóa thành dạng "Nguyễn Văn An, Trần Thị Lan, Lê Minh Hùng"

function chuanHoaTen(ten) {
	return ten
		.trim() // Xóa khoảng trắng đầu cuối
		.toLowerCase() // Chuyển thành chữ thường
		.split(' ') // Tách thành mảng từ
		.filter((tu) => tu !== '') // Loại bỏ từ rỗng
		.map((tu) => tu.charAt(0).toUpperCase() + tu.slice(1)) // Viết hoa chữ cái đầu
		.join(' '); // Nối lại
}

const danhSachSach = danhSachLop.split(',').map(chuanHoaTen).join(', ');

console.log(danhSachSach); // "Nguyễn Văn An, Trần Thị Lan, Lê Minh Hùng"
```

### Bài 7: Tạo slug URL từ tiêu đề

```javascript
const tieuDe = 'Bài Kiểm Tra Toán Học Lớp 10A1 - Tháng 3/2024';

// Chuyển thành slug: bai-kiem-tra-toan-hoc-lop-10a1-thang-3-2024

function taoSlug(chuoi) {
	return chuoi
		.toLowerCase() // Chuyển thường
		.replace(/[àáạảãâầấậẩẫăằắặẳẵ]/g, 'a') // Thay thế ký tự có dấu
		.replace(/[èéẹẻẽêềếệểễ]/g, 'e')
		.replace(/[ìíịỉĩ]/g, 'i')
		.replace(/[òóọỏõôồốộổỗơờớợởỡ]/g, 'o')
		.replace(/[ùúụủũưừứựửữ]/g, 'u')
		.replace(/[ỳýỵỷỹ]/g, 'y')
		.replace(/đ/g, 'd')
		.replace(/[^a-z0-9\s-]/g, '') // Xóa ký tự đặc biệt
		.replace(/\s+/g, '-') // Thay khoảng trắng bằng dấu gạch ngang
		.replace(/-+/g, '-') // Xóa dấu gạch ngang thừa
		.replace(/^-|-$/g, ''); // Xóa dấu gạch ngang đầu/cuối
}

console.log(taoSlug(tieuDe)); // "bai-kiem-tra-toan-hoc-lop-10a1-thang-3-2024"
```

### Bài 8: Kiểm tra mật khẩu mạnh

```javascript
const matKhau = 'MyPassword123!';

// Kiểm tra mật khẩu có:
// - Ít nhất 8 ký tự
// - Có chữ hoa
// - Có chữ thường
// - Có số
// - Có ký tự đặc biệt

function kiemTraMatKhau(mk) {
	const checks = {
		doDai: mk.length >= 8,
		coChuHoa: /[A-Z]/.test(mk),
		coChuThuong: /[a-z]/.test(mk),
		coSo: /\d/.test(mk),
		coKyTuDacBiet: /[!@#$%^&*(),.?":{}|<>]/.test(mk),
	};

	const mangKetQua = Object.keys(checks).filter((key) => !checks[key]);

	if (mangKetQua.length === 0) {
		return 'Mật khẩu mạnh! ✅';
	} else {
		return `Mật khẩu yếu! Thiếu: ${mangKetQua.join(', ')} ❌`;
	}
}

console.log(kiemTraMatKhau(matKhau)); // "Mật khẩu mạnh! ✅"
console.log(kiemTraMatKhau('123456')); // "Mật khẩu yếu! Thiếu: doDai, coChuHoa, coChuThuong, coKyTuDacBiet ❌"
```

### Bài 9: Tạo initials từ họ tên

```javascript
const danhSachHocSinh = ['Nguyễn Văn An', 'Trần Thị Bích Lan', 'Lê Minh Hùng', 'Phạm Thu Hương'];

// Tạo initials: NVA, TTBL, LMH, PTH

function taoInitials(hoTen) {
	return hoTen
		.split(' ')
		.map((tu) => tu.charAt(0).toUpperCase())
		.join('');
}

const danhSachInitials = danhSachHocSinh.map(taoInitials);
console.log(danhSachInitials); // ["NVA", "TTBL", "LMH", "PTH"]

// Tạo bảng danh sách
danhSachHocSinh.forEach((ten, index) => {
	console.log(`${danhSachInitials[index]}: ${ten}`);
});
// NVA: Nguyễn Văn An
// TTBL: Trần Thị Bích Lan
// LMH: Lê Minh Hùng
// PTH: Phạm Thu Hương
```

### Bài 10: Parser CSV đơn giản

```javascript
const duLieuCSV = `Tên,Lớp,Toán,Lý,Hóa
An,10A1,8,7,9
Lan,10A2,9,8,7
Hùng,10A1,7,9,8`;

// Parse thành object

function parseCSV(csvString) {
	const dong = csvString.split('\n');
	const tieuDe = dong[0].split(',');
	const duLieu = [];

	for (let i = 1; i < dong.length; i++) {
		const giaTri = dong[i].split(',');
		const doiTuong = {};

		tieuDe.forEach((ten, index) => {
			doiTuong[ten] = giaTri[index];
		});

		duLieu.push(doiTuong);
	}

	return duLieu;
}

const ketQua = parseCSV(duLieuCSV);
console.log(ketQua);
// [
//   { "Tên": "An", "Lớp": "10A1", "Toán": "8", "Lý": "7", "Hóa": "9" },
//   { "Tên": "Lan", "Lớp": "10A2", "Toán": "9", "Lý": "8", "Hóa": "7" },
//   { "Tên": "Hùng", "Lớp": "10A1", "Toán": "7", "Lý": "9", "Hóa": "8" }
// ]

// Tính điểm trung bình cho từng học sinh
ketQua.forEach((hocSinh) => {
	const diemTB = (parseInt(hocSinh.Toán) + parseInt(hocSinh.Lý) + parseInt(hocSinh.Hóa)) / 3;
	console.log(`${hocSinh.Tên}: ${diemTB.toFixed(1)} điểm`);
});
// An: 8.0 điểm
// Lan: 8.0 điểm
// Hùng: 8.0 điểm
```

---

## 11. Tham khảo đầy đủ

### 📋 Phương thức cơ bản

| Phương thức         | Chức năng            | Ví dụ                   |
| ------------------- | -------------------- | ----------------------- |
| `charAt(pos)`       | Lấy ký tự tại vị trí | `str.charAt(0)`         |
| `length`            | Độ dài chuỗi         | `str.length`            |
| `indexOf(text)`     | Tìm vị trí đầu tiên  | `str.indexOf("a")`      |
| `includes(text)`    | Kiểm tra có chứa     | `str.includes("hello")` |
| `slice(start, end)` | Cắt chuỗi            | `str.slice(0, 5)`       |
| `split(separator)`  | Tách thành mảng      | `str.split(",")`        |
| `replace(old, new)` | Thay thế             | `str.replace("a", "b")` |
| `toUpperCase()`     | Chuyển HOA           | `str.toUpperCase()`     |
| `toLowerCase()`     | Chuyển thường        | `str.toLowerCase()`     |
| `trim()`            | Xóa khoảng trắng     | `str.trim()`            |

### 🔍 Phương thức tìm kiếm

| Phương thức         | Chức năng            | Trả về         | Ví dụ                   |
| ------------------- | -------------------- | -------------- | ----------------------- |
| `indexOf(text)`     | Tìm vị trí đầu tiên  | Số hoặc -1     | `str.indexOf("An")`     |
| `lastIndexOf(text)` | Tìm vị trí cuối cùng | Số hoặc -1     | `str.lastIndexOf("An")` |
| `search(pattern)`   | Tìm kiếm nâng cao    | Số hoặc -1     | `str.search(/\d+/)`     |
| `includes(text)`    | Kiểm tra có chứa     | true/false     | `str.includes("@")`     |
| `startsWith(text)`  | Bắt đầu bằng         | true/false     | `str.startsWith("Xin")` |
| `endsWith(text)`    | Kết thúc bằng        | true/false     | `str.endsWith(".vn")`   |
| `match(pattern)`    | Tìm theo mẫu         | Mảng hoặc null | `str.match(/\d+/g)`     |

### ✂️ Phương thức cắt và nối

| Phương thức             | Chức năng       | Thay đổi gốc? | Ví dụ                 |
| ----------------------- | --------------- | ------------- | --------------------- |
| `slice(start, end)`     | Cắt theo vị trí | Không         | `str.slice(1, 5)`     |
| `substring(start, end)` | Cắt (không âm)  | Không         | `str.substring(1, 5)` |
| `substr(start, length)` | Cắt theo độ dài | Không         | `str.substr(1, 3)`    |
| `concat(str2)`          | Nối chuỗi       | Không         | `str1.concat(str2)`   |
| `split(sep)`            | Tách thành mảng | Không         | `str.split(" ")`      |

### 🔄 Phương thức biến đổi

| Phương thức              | Chức năng              | Ví dụ                      |
| ------------------------ | ---------------------- | -------------------------- |
| `toUpperCase()`          | Chuyển HOA             | `str.toUpperCase()`        |
| `toLowerCase()`          | Chuyển thường          | `str.toLowerCase()`        |
| `trim()`                 | Xóa khoảng trắng 2 đầu | `str.trim()`               |
| `trimStart()`            | Xóa khoảng trắng đầu   | `str.trimStart()`          |
| `trimEnd()`              | Xóa khoảng trắng cuối  | `str.trimEnd()`            |
| `replace(old, new)`      | Thay thế đầu tiên      | `str.replace("a", "b")`    |
| `replaceAll(old, new)`   | Thay thế tất cả        | `str.replaceAll("a", "b")` |
| `repeat(count)`          | Lặp lại                | `str.repeat(3)`            |
| `padStart(length, char)` | Thêm ký tự vào đầu     | `str.padStart(5, "0")`     |
| `padEnd(length, char)`   | Thêm ký tự vào cuối    | `str.padEnd(5, "*")`       |

### 🎭 Phương thức kiểm tra và truy cập

| Phương thức          | Chức năng                | Ví dụ                |
| -------------------- | ------------------------ | -------------------- |
| `charAt(index)`      | Lấy ký tự tại vị trí     | `str.charAt(0)`      |
| `charCodeAt(index)`  | Lấy mã ASCII             | `str.charCodeAt(0)`  |
| `at(index)`          | Lấy ký tự (hỗ trợ số âm) | `str.at(-1)`         |
| `codePointAt(index)` | Lấy Unicode point        | `str.codePointAt(0)` |

### 🆕 Template Strings (ES6+)

```javascript
// Cú pháp cơ bản
const name = 'An';
const message = `Xin chào ${name}!`;

// Nhiều dòng
const poem = `
Dòng 1
Dòng 2  
Dòng 3
`;

// Biểu thức
const result = `Tổng: ${5 + 3}`;
const status = `Kết quả: ${score >= 8 ? 'Đạt' : 'Không đạt'}`;

// HTML Template
const html = `
<div class="student-card">
  <h3>${name}</h3>
  <p>Điểm: ${score}</p>
</div>
`;
```

### 🔤 Phương thức Unicode và Encoding

| Phương thức              | Chức năng             | Ví dụ                           |
| ------------------------ | --------------------- | ------------------------------- |
| `String.fromCharCode()`  | Tạo chuỗi từ mã ASCII | `String.fromCharCode(65)`       |
| `String.fromCodePoint()` | Tạo chuỗi từ Unicode  | `String.fromCodePoint(0x1F60E)` |
| `normalize()`            | Chuẩn hóa Unicode     | `str.normalize("NFD")`          |
| `localeCompare()`        | So sánh theo ngôn ngữ | `str1.localeCompare(str2)`      |

---

## 12. Tóm tắt

-   **Chuỗi** dùng để lưu trữ văn bản, ký tự
-   **Vị trí** bắt đầu từ 0, không phải 1
-   Sử dụng `length` để biết độ dài chuỗi
-   **Tìm kiếm**: `indexOf`, `includes`, `search`
-   **Cắt chuỗi**: `slice`, `substring`
-   **Biến đổi**: `toUpperCase`, `toLowerCase`, `trim`
-   **Template Strings** với backtick (`) để tạo chuỗi linh hoạt
-   **Chuỗi không thể thay đổi** - các phương thức luôn trả về chuỗi mới

**Lưu ý quan trọng:** Chuỗi trong JavaScript **không thể thay đổi** (immutable). Mọi phương thức đều trả về chuỗi mới, không sửa chuỗi gốc!

**Tip học tập:** Hãy thực hành với dữ liệu thực tế như tên học sinh, địa chỉ email, số điện thoại để hiểu rõ cách áp dụng!

**Mẹo debug:** Dùng `console.log()` để kiểm tra kết quả từng bước, đặc biệt khi dùng nhiều phương thức nối tiếp nhau như `str.trim().toLowerCase().split(' ')`.
