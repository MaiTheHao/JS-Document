## Biến (Variable) trong JavaScript

### 1. Biến là gì?

Biến là một "chiếc hộp" trong bộ nhớ máy tính dùng để lưu trữ giá trị. Giá trị này có thể thay đổi trong quá trình chạy chương trình.

### 2. Các cách khai báo biến

JavaScript hỗ trợ ba từ khóa để khai báo biến:

-   **`var`**:

    -   Được sử dụng từ lâu, nhưng có phạm vi (scope) rộng hơn mong muốn (toàn cục hoặc trong hàm).
    -   Dễ gây lỗi do phạm vi không rõ ràng.

-   **`let`**:

    -   Khai báo biến với phạm vi khối (block-level scope).
    -   Có thể thay đổi giá trị sau khi khai báo.

-   **`const`**:
    -   Khai báo một hằng số (giá trị không thay đổi sau khi gán).
    -   Cũng có phạm vi khối như `let`.

> **Khuyến nghị:** Nên dùng `let` và `const` thay cho `var` để tránh lỗi về phạm vi.

> **Tham khảo thêm:** [Scope trong JavaScript](../Phạm%20vi%20Scope/README.md)

#### Ví dụ:

```javascript
let x = 5; // x có thể thay đổi giá trị
const y = 10; // y là hằng số, không thể thay đổi giá trị
var z = 15; // z có thể thay đổi giá trị, nhưng phạm vi rộng (toàn cục hoặc trong hàm)
```

---

## Kiểu dữ liệu (Datatype) trong JavaScript

### 1. Kiểu dữ liệu là gì?

Kiểu dữ liệu xác định loại giá trị mà biến có thể lưu trữ. JavaScript có hai nhóm kiểu dữ liệu chính:

-   **Kiểu nguyên thủy (Primitive)**
-   **Kiểu tham chiếu (Non-Primitive/Reference)**

### 2. Kiểu dữ liệu nguyên thủy (Primitive)

Đây là các giá trị đơn giản, không thể thay đổi nội dung bên trong (immutable):

-   **Number**: Số (nguyên, thực)
    -   _Ví dụ:_ `let num = 42;`
-   **String**: Chuỗi ký tự
    -   _Ví dụ:_ `let name = "DuckMin";`
-   **Boolean**: Đúng hoặc sai (`true` hoặc `false`)
    -   _Ví dụ:_ `let isActive = false;`
-   **Undefined**: Biến được khai báo nhưng chưa gán giá trị
    -   _Ví dụ:_ `let x; // x là undefined`
-   **Null**: Biến không có giá trị (cố ý gán rỗng)
    -   _Ví dụ:_ `let emptyValue = null;`
-   **Symbol** (ES6+): Tạo giá trị duy nhất, thường dùng làm key cho object
    -   _Ví dụ:_ `let uniqueSymbol = Symbol("desc");`
-   **BigInt** (ES11+): Lưu trữ số nguyên rất lớn
    -   _Ví dụ:_ `let big = BigInt(12345678901234567890);`

#### Sự khác biệt giữa `undefined` và `null`

-   **`undefined`** là giá trị mặc định của một biến khi bạn khai báo nhưng chưa gán giá trị cho nó. Nó cũng xuất hiện khi một hàm không trả về gì.
    -   _Ví dụ:_
    ```javascript
    let a;
    console.log(a); // undefined
    ```
-   **`null`** là một giá trị đặc biệt mà bạn chủ động gán cho biến để thể hiện rằng biến đó "không có giá trị" hoặc "rỗng".
    -   _Ví dụ:_
    ```javascript
    let b = null;
    console.log(b); // null
    ```

> **Lưu ý:** `undefined` và `null` đều mang ý nghĩa "không có giá trị", nhưng `undefined` là do JavaScript tự gán, còn `null` là do lập trình viên chủ động gán.

### 3. Kiểu dữ liệu tham chiếu (Non-Primitive/Reference)

Đây là các kiểu phức tạp, có thể chứa nhiều giá trị và thay đổi nội dung bên trong:

-   **Object**: Lưu trữ cặp khóa-giá trị
    -   _Ví dụ:_
    ```javascript
    let person = {
    	name: 'DuckMin',
    	age: 18,
    	isStudent: true,
    };
    ```
-   **Array**: Danh sách các giá trị (một dạng đặc biệt của object)
    -   _Ví dụ:_
    ```javascript
    let fruits = ['apple', 'banana', 'cherry'];
    ```
-   **Function**: Hàm cũng là một kiểu dữ liệu, có thể gán cho biến
    -   _Ví dụ:_
    ```javascript
    function greet() {
    	console.log('Hello, world!');
    }
    ```

---

### Tóm tắt

1. **Biến** là nơi lưu trữ giá trị. Khai báo bằng `var`, `let`, hoặc `const`. Nên ưu tiên `let` và `const`.
2. **Kiểu dữ liệu** xác định loại giá trị biến có thể lưu trữ:
    - **Nguyên thủy:** `Number`, `String`, `Boolean`, `Undefined`, `Null`, `Symbol`, `BigInt`
    - **Tham chiếu:** `Object`, `Array`, `Function`
