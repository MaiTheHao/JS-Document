# 🎯 JavaScript Operators

## 📝 Giới thiệu
***Operators (toán tử)*** trong JavaScript là các ký hiệu hoặc từ khóa đặc biệt được sử dụng để:

✨ Các ứng dụng chính:
- 🔸 Thực hiện các phép toán trên biến và giá trị
- 🔸 Thao tác với dữ liệu một cách linh hoạt
- 🔸 Xử lý từ các phép tính đơn giản đến phức tạp

> **Note:** Toán tử là thành phần cơ bản không thể thiếu trong lập trình JavaScript!

## Các loại toán tử trong JavaScript

JavaScript hỗ trợ **8 loại toán tử chính**:

1. **Arithmetic Operators** _(Toán tử số học)_
2. **Assignment Operators** _(Toán tử gán)_
3. **Comparison Operators** _(Toán tử so sánh)_
4. **String Operators** _(Toán tử chuỗi)_
5. **Logical Operators** _(Toán tử logic)_
6. **Bitwise Operators** _(Toán tử bitwise)_
7. **Ternary Operator** _(Toán tử ba ngôi)_
8. **Type Operators** _(Toán tử kiểu dữ liệu)_

## 1. Arithmetic Operators

> **Quan trọng:** Đây là các toán tử cơ bản nhất trong JavaScript!

| Toán tử | Mô tả | Ví dụ |
|:-------:|-------|-------|
| `+` | Cộng | `5 + 2 = 7` |
| `-` | Trừ | `5 - 2 = 3` |
| `*` | Nhân | `5 * 2 = 10` |
| `/` | Chia | `5 / 2 = 2.5` |
| `%` | Chia lấy dư | `5 % 2 = 1` |
| `**` | Lũy thừa | `5 ** 2 = 25` |
| `++` | Tăng một đơn vị | `let a = 5; a++; // a = 6` |
| `--` | Giảm một đơn vị | `let a = 5; a--; // a = 4` |

## 2. Assignment Operators

| Toán tử | Ví dụ | Tương đương |
|:-------:|-------|-------------|
| `=` | `x = 10` | - |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `%=` | `x %= 5` | `x = x % 5` |
| `**=` | `x **= 2` | `x = x ** 2` |

## 3. Comparison Operators

> **Tip:** Luôn ưu tiên sử dụng `===` thay vì `==` để tránh các lỗi không mong muốn!

| Toán tử | Mô tả | Ví dụ & Kết quả |
|:-------:|-------|-----------------|
| `==` | So sánh bằng (loose) | `5 == '5' // ✅ true` |
| `===` | So sánh bằng nghiêm ngặt | `5 === '5' // ❌ false` |
| `!=` | Không bằng (loose) | `5 != '6' // ✅ true` |
| `!==` | Không bằng nghiêm ngặt | `5 !== '5' // ✅ true` |
| `>` | Lớn hơn | `5 > 3 // ✅ true` |
| `<` | Nhỏ hơn | `5 < 3 // ❌ false` |
| `>=` | Lớn hơn hoặc bằng | `5 >= 5 // ✅ true` |
| `<=` | Nhỏ hơn hoặc bằng | `5 <= 3 // ❌ false` |

## 4. String Operators

Dùng để nối chuỗi.

| Toán tử | Mô tả | Ví dụ |
|:-------:|-------|-------|
| `+` | Nối chuỗi | `'Hello' + ' World' = 'Hello World'` |
| `+=` | Nối và gán | `let str = 'Hello'; str += ' World'; // str = 'Hello World'` |

## 5. Logical Operators

Dùng để thực hiện các phép toán logic.

| Toán tử | Mô tả | Ví dụ |
|:-------:|-------|-------|
| `&&` | Và | `(true && false) = false` |
| `\|\|` | Hoặc | `(true \|\| false) = true` |
| `!` | Phủ định | `!true = false` |

## 6. Bitwise Operators

Dùng để thực hiện các phép toán trên bit.

| Toán tử | Mô tả | Ví dụ |
|:-------:|-------|-------|
| `&` | AND bitwise | `5 & 1 = 1` |
| `\|` | OR bitwise | `5 \| 1 = 5` |
| `^` | XOR bitwise | `5 ^ 1 = 4` |
| `~` | NOT bitwise | `~5 = -6` |
| `<<` | Dịch trái | `5 << 1 = 10` |
| `>>` | Dịch phải | `5 >> 1 = 2` |
| `>>>` | Dịch phải không dấu | `5 >>> 1 = 2` |

## 7. Ternary Operator

Dùng để viết gọn câu lệnh điều kiện.

```js
let result = (5 > 3) ? 'Yes' : 'No'; // 'Yes'
```

## 8. Type Operators

Dùng để kiểm tra kiểu dữ liệu.

| Toán tử | Mô tả | Ví dụ |
|:-------:|-------|-------|
| `typeof` | Kiểm tra kiểu | `typeof 'Hello' // 'string'` |
| `instanceof` | Kiểm tra đối tượng thuộc lớp nào | `[] instanceof Array // true` |

## Best Practices

1. **Ưu tiên sử dụng `===`** thay vì `==` để tránh type coercion (ép kiểu)
2. **Cẩn thận với toán tử `++` và `--`** khi đặt trước hoặc sau biến
3. **Sử dụng dấu ngoặc `()`** để làm rõ thứ tự ưu tiên của các toán tử
4. **Tránh lạm dụng toán tử ba ngôi** cho các điều kiện phức tạp

> **Pro tip:** Hiểu rõ về operator precedence (độ ưu tiên của toán tử) sẽ giúp bạn viết code chính xác và dễ đọc hơn!