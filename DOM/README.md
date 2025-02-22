# DOM và HTML DOM

## DOM (Document Object Model)

-   DOM là một mô hình lập trình tiêu chuẩn của W3C cho các tài liệu HTML và XML.
-   Cấu trúc tài liệu được biểu diễn dưới dạng cây với các nút bao gồm:
    -   **Phần tử (elements)**: Các thẻ HTML/XML.
    -   **Thuộc tính (attributes)**: Các thuộc tính của phần tử.
    -   **Văn bản (text)**: Nội dung giữa các thẻ.
-   DOM cung cấp khả năng truy cập và thay đổi nội dung, cấu trúc, và kiểu dáng của tài liệu.

## HTML DOM

-   HTML DOM là tiêu chuẩn đối tượng và giao diện lập trình dành cho HTML.
-   Định nghĩa:
    -   Các phần tử HTML dưới dạng đối tượng.
    -   Thuộc tính, phương thức và sự kiện cho các phần tử HTML.
-   Tính năng:
    -   Cho phép **truy xuất, thay đổi, thêm hoặc xóa** các phần tử HTML.

---

# Khả năng của JavaScript với HTML DOM

-   Thay đổi phần tử, thuộc tính, và kiểu CSS.
-   Thêm hoặc xóa phần tử và thuộc tính.
-   Xử lý hoặc tạo sự kiện mới.

---

# Các Phương Thức Cơ Bản của DOM (DOM core) và HTML DOM

| Phương thức                            | DOM Core   | HTML DOM   |
|----------------------------------------|:----------:|:----------:|
| `getElementById(id)`                   | ❌         | ✔️        |
| `getElementsByClassName(className)`    | ❌         | ✔️        |
| `getElementsByTagName(tagName)`        | ✔️         | ✔️        |
| `querySelector(selector)`              | ❌         | ✔️        |
| `querySelectorAll(selector)`           | ❌         | ✔️        |
| `createElement(tagName)`               | ✔️         | ✔️        |
| `appendChild(node)`                    | ✔️         | ✔️        |
| `removeChild(node)`                    | ✔️         | ✔️        |
| `replaceChild(newNode, oldNode)`       | ✔️         | ✔️        |
| `setAttribute(name, value)`            | ❌         | ✔️        |
| `getAttribute(name)`                   | ❌         | ✔️        |
| `addEventListener(event, function)`    | ❌         | ✔️        |
| `removeEventListener(event, function)` | ❌         | ✔️        |

-   `getElementById(id)`: Lấy phần tử dựa trên `id`.
-   `getElementsByClassName(className)`: Trả về danh sách các phần tử có `class` được chỉ định.
-   `getElementsByTagName(tagName)`: Trả về danh sách các phần tử có tên thẻ được chỉ định.
-   `querySelector(selector)`: Trả về phần tử đầu tiên khớp với bộ chọn CSS.
-   `querySelectorAll(selector)`: Trả về danh sách các phần tử khớp với bộ chọn CSS.
-   `createElement(tagName)`: Tạo một phần tử HTML mới.
-   `appendChild(node)`: Thêm một nút con vào phần tử cha.
-   `removeChild(node)`: Xóa một nút con khỏi phần tử cha.
-   `replaceChild(newNode, oldNode)`: Thay thế một nút con.
-   `setAttribute(name, value)`: Thiết lập giá trị thuộc tính.
-   `getAttribute(name)`: Lấy giá trị thuộc tính.
-   `addEventListener(event, function)`: Thêm sự kiện cho phần tử.
-   `removeEventListener(event, function)`: Loại bỏ sự kiện khỏi phần tử.

---

# Event Bubbling và Event Capturing

-   **Event Bubbling**: Sự kiện lan từ phần tử con đến cha.
-   **Event Capturing**: Sự kiện lan từ phần tử cha đến con.

---

# Tiêu Chuẩn DOM của W3C
*W3C (World Wide Web Consortium) là tổ chức quốc tế phát triển các tiêu chuẩn cho World Wide Web. W3C được thành lập bởi Tim Berners-Lee, người phát minh ra World Wide Web, với mục tiêu đảm bảo rằng các tiêu chuẩn web được phát triển một cách đồng nhất và có thể tương thích trên nhiều nền tảng và thiết bị khác nhau.*

-   **Core DOM**: Mô hình chung cho tất cả các loại tài liệu.
-   **XML DOM**: Mô hình cho tài liệu XML.
-   **HTML DOM**: Mô hình cho tài liệu HTML.

---

# Luyện Tập

1.  **Thay đổi màu nền của một phần tử khi click vào nó.**
2.  **Thêm một phần tử mới vào cuối danh sách.**
3.  **Xóa một phần tử khỏi danh sách.**
4.  **Thay đổi kích thước của một phần tử.**
5.  **Hiển thị một thông báo khi chuột di chuyển qua một phần tử.**
6.  **Hiển thị một thông báo khi một phần tử được click.**
_Danh sách bài giải ở đây [**solves**](./solves)_

## Các bài tập thú vị hơn (không có sẵn lời giải)

1. **Kéo thả ô từ vị trí này sang vị trí khác**
2. **Nhập thể 2 block và tăng kích thước**
3. **Tic-Tac-Toe**
4. **Image Gallery**