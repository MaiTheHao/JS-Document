## Variables trong JavaScript

#### 1. Khái niệm về Biến (variables):

Biến trong JavaScript là một đại diện trong bộ nhớ máy tính để lưu trữ giá trị. Các giá trị này có thể được thay đổi trong suốt quá trình thực thi của chương trình.

#### 2. Các Từ Khóa Khai Báo Biến:

JavaScript hỗ trợ ba từ khóa chính để khai báo biến:

- `var`:

    - Được sử dụng từ lâu, nhưng có một số vấn đề về phạm vi *(scope)*. Biến khai báo bằng `var` có phạm vi toàn cục *(global)* hoặc phạm vi trong một hàm *(function scope)*.
    
- `let`:

    - `let` khai báo biến với phạm vi khối (block-level scope), có thể thay đổi giá trị trong suốt quá trình thực thi.
    
- `const`:

    - Được sử dụng để khai báo hằng số. Một khi đã gán giá trị cho biến `const`, bạn không thể thay đổi giá trị của nó.

#### 3. Ví Dụ:

``` Javascript
let x = 5;      // x là biến có thể thay đổi giá trị
const y = 10;    // y là hằng số, không thể thay đổi giá trị
var z = 15;      // z là biến có thể thay đổi giá trị, nhưng phạm vi toàn cục hoặc trong hàm
```

---

## Datatypes (Kiểu Dữ Liệu) trong JavaScript

#### Khái Niệm về Kiểu Dữ Liệu:

Trong Javascript, kiểu dữ liệu xác định loại của giá trị mà một biến có thể lưu trữ. 
JavaScript có hai loại kiểu dữ liệu chính: **Primitive** (*Nguyên thủy*) và **Non-Primitive** (*Tham chiếu*).

#### 1. Primitive Data Types (Kiểu Dữ Liệu Nguyên Thủy):

Các kiểu dữ liệu này bao gồm các giá trị đơn giản và không thể thay đổi.

- `Number`: Dùng để biểu diễn các giá trị số (nguyên và thực).
  - *Ví dụ: `let num = 42;`*

- `String`: Dùng để lưu trữ chuỗi văn bản.
    - *Ví dụ: `let name = "DuckMin";`*

- `Boolean`: Dùng để lưu trữ hai giá trị: true hoặc false.
    - *Ví dụ: `let isActive = false;`*

- `Undefined`: Khi một biến được khai báo nhưng chưa được gán giá trị, nó có giá trị mặc định là undefined.
    - *Ví dụ: `let x; // x là undefined`*

- `Null`: Một giá trị đặc biệt để chỉ rằng biến không có giá trị.
    - *Ví dụ: `let emptyValue = null;`*

- `Symbol` *(ES6+)*: Dùng để tạo các giá trị duy nhất và không thay đổi.
    - *Ví dụ: `let uniqueSymbol = Symbol("description");`*
    
- `BigInt` *(ES11+)*: Dùng để đại diện cho các số nguyên lớn hơn giới hạn của kiểu Number.
    - *Ví dụ: `let largeNumber = BigInt(1234567890123456789012345678901234567890);`*

#### 2. Non-Primitive Data Types (Kiểu Dữ Liệu Tham Chiếu):

Đây là những kiểu dữ liệu phức tạp, có thể lưu trữ nhiều giá trị và có thể thay đổi.

- `Object`: Dùng để lưu trữ các cặp khóa-giá trị. Đối tượng có thể chứa nhiều giá trị khác nhau.

*Ví dụ:*

```javascript
let person = {
  name: "DuckMin",
  age: 18,
  isStudent: true
};
```

- `Array`: Là một loại đối tượng đặc biệt trong JavaScript, dùng để lưu trữ danh sách các giá trị.

*Ví dụ:*

```javascript
let fruits = ["apple", "banana", "cherry"];
```

- `Function`: Trong JavaScript, hàm cũng là một đối tượng và có thể được sử dụng như một kiểu dữ liệu.

*Ví dụ:*

```javascript
function greet() {
  console.log("Hello, world!");
}
```

----

##### Tóm lại:

1. Biến *(Variables)* trong JavaScript dùng để lưu trữ giá trị. Bạn có thể khai báo biến bằng `var`, `let`, hoặc `const`.

   - `let` và `const` là lựa chọn hiện đại, tránh được các vấn đề liên quan đến phạm vi của `var`.
   
3. Kiểu Dữ Liệu *(Datatypes)* xác định loại của giá trị mà một biến có thể lưu trữ. JavaScript có hai loại kiểu dữ liệu chính:

   - Kiểu dữ liệu nguyên thủy *(Primitive)*: `Number`, `String`, `Boolean`, `Undefined`, `Null`, `Symbol`, `BigInt`.
   - Kiểu dữ liệu tham chiếu *(Non-Primitive)*: `Object`, `Array`, `Function`.
