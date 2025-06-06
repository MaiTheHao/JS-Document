# DOM và HTML DOM

## DOM (Document Object Model)

-   DOM là một mô hình lập trình tiêu chuẩn của W3C cho các tài liệu HTML và XML.
-   Cấu trúc tài liệu được biểu diễn dưới dạng cây với các nút bao gồm:
    -   **Phần tử (elements)**: Các thẻ HTML/XML.
    -   **Thuộc tính (attributes)**: Các thuộc tính của phần tử.
    -   **Văn bản (text)**: Nội dung giữa các thẻ.
-   DOM cung cấp khả năng truy cập và thay đổi nội dung, cấu trúc, và kiểu dáng của tài liệu.

### Kiến Trúc Cây DOM (DOM Tree Architecture)

DOM biểu diễn tài liệu HTML/XML như một cấu trúc cây phân cấp với các đặc điểm:

-   **Root Node**: `document` - nút gốc của toàn bộ tài liệu
-   **Element Nodes**: Các thẻ HTML (`<div>`, `<p>`, `<span>`, etc.)
-   **Text Nodes**: Nội dung văn bản bên trong các element
-   **Attribute Nodes**: Các thuộc tính của element (`id`, `class`, `src`, etc.)
-   **Comment Nodes**: Các comment HTML (`<!-- -->`)

### Các Kiểu Dữ Liệu Cơ Bản trong DOM

| Kiểu Dữ Liệu     | Mô Tả                                                      |
| ---------------- | ---------------------------------------------------------- |
| `Document`       | Đối tượng đại diện cho toàn bộ tài liệu HTML               |
| `Node`           | Đối tượng cơ sở cho tất cả các nút trong DOM tree          |
| `Element`        | Đối tượng đại diện cho các thẻ HTML                        |
| `NodeList`       | Mảng các node, trả về từ `querySelectorAll()`              |
| `HTMLCollection` | Collection các element, trả về từ `getElementsByTagName()` |
| `Attr`           | Đối tượng đại diện cho thuộc tính của element              |

## HTML DOM

-   HTML DOM là tiêu chuẩn đối tượng và giao diện lập trình dành cho HTML.
-   Định nghĩa:
    -   Các phần tử HTML dưới dạng đối tượng.
    -   Thuộc tính, phương thức và sự kiện cho các phần tử HTML.
-   Tính năng:
    -   Cho phép **truy xuất, thay đổi, thêm hoặc xóa** các phần tử HTML.

### Giao Diện và Đối Tượng DOM

HTML DOM cung cấp các giao diện chuyên biệt:

-   **HTMLElement**: Giao diện cơ sở cho tất cả các element HTML
-   **HTMLTableElement**: Giao diện chuyên biệt cho `<table>`
-   **HTMLInputElement**: Giao diện chuyên biệt cho `<input>`
-   **HTMLFormElement**: Giao diện chuyên biệt cho `<form>`

---

# Khả năng của JavaScript với HTML DOM

-   Thay đổi phần tử, thuộc tính, và kiểu CSS.
-   Thêm hoặc xóa phần tử và thuộc tính.
-   Xử lý hoặc tạo sự kiện mới.

### Chi Tiết Khả Năng DOM Manipulation

1. **Truy Cập Elements**:

    - Tìm kiếm element theo ID, class, tag name
    - Sử dụng CSS selectors phức tạp
    - Duyệt cây DOM thông qua parent/child relationships

2. **Thao Tác Nội Dung**:

    - Thay đổi `textContent`, `innerHTML`, `innerText`
    - Thêm/xóa/sửa đổi attributes
    - Thay đổi CSS styles thông qua `style` property

3. **Thao Tác Cấu Trúc**:
    - Tạo elements mới với `createElement()`
    - Thêm elements với `appendChild()`, `insertBefore()`
    - Xóa elements với `removeChild()`, `remove()`
    - Di chuyển elements trong DOM tree

---

# Các Phương Thức Cơ Bản của DOM (DOM core) và HTML DOM

| Phương thức                            | DOM Core | HTML DOM | Mô Tả Chi Tiết                               |
| -------------------------------------- | :------: | :------: | -------------------------------------------- |
| `getElementById(id)`                   |    ❌    |    ✔️    | Trả về element có ID cụ thể (duy nhất)       |
| `getElementsByClassName(className)`    |    ❌    |    ✔️    | Trả về HTMLCollection các element có class   |
| `getElementsByTagName(tagName)`        |    ✔️    |    ✔️    | Trả về HTMLCollection các element theo tag   |
| `querySelector(selector)`              |    ❌    |    ✔️    | Trả về element đầu tiên khớp CSS selector    |
| `querySelectorAll(selector)`           |    ❌    |    ✔️    | Trả về NodeList tất cả element khớp selector |
| `createElement(tagName)`               |    ✔️    |    ✔️    | Tạo element mới (chưa được thêm vào DOM)     |
| `appendChild(node)`                    |    ✔️    |    ✔️    | Thêm node làm con cuối cùng                  |
| `removeChild(node)`                    |    ✔️    |    ✔️    | Xóa node con cụ thể                          |
| `replaceChild(newNode, oldNode)`       |    ✔️    |    ✔️    | Thay thế node con                            |
| `setAttribute(name, value)`            |    ❌    |    ✔️    | Thiết lập attribute với giá trị              |
| `getAttribute(name)`                   |    ❌    |    ✔️    | Lấy giá trị attribute                        |
| `addEventListener(event, function)`    |    ❌    |    ✔️    | Đăng ký event listener                       |
| `removeEventListener(event, function)` |    ❌    |    ✔️    | Loại bỏ event listener                       |

### Phương Thức Selector Nâng Cao

```javascript
// CSS Selectors phức tạp
document.querySelector('p.warning, p.note'); // Multiple selectors
document.querySelector('#main > .content'); // Direct child
document.querySelector("input[type='text']"); // Attribute selector
```

### Node Navigation Properties

| Property          | Mô Tả                    |
| ----------------- | ------------------------ |
| `parentNode`      | Node cha                 |
| `childNodes`      | NodeList tất cả node con |
| `firstChild`      | Node con đầu tiên        |
| `lastChild`       | Node con cuối cùng       |
| `nextSibling`     | Node anh em kế tiếp      |
| `previousSibling` | Node anh em trước đó     |

---

# Event Handling trong DOM

## Event System

Events là tín hiệu được trình duyệt phát ra khi có điều gì đó xảy ra trong hệ thống:

### Các Loại Event Phổ Biến

| Event Type      | Mô Tả            | Ví Dụ                            |
| --------------- | ---------------- | -------------------------------- |
| Mouse Events    | Sự kiện chuột    | `click`, `mouseover`, `mouseout` |
| Keyboard Events | Sự kiện bàn phím | `keydown`, `keyup`, `keypress`   |
| Form Events     | Sự kiện form     | `submit`, `focus`, `blur`        |
| Window Events   | Sự kiện window   | `load`, `resize`, `scroll`       |

### Event Object

Mỗi event handler nhận một `event object` chứa thông tin về sự kiện:

```javascript
element.addEventListener('click', function (event) {
	console.log(event.target); // Element được click
	console.log(event.type); // Loại event ('click')
	console.log(event.timeStamp); // Thời gian xảy ra event
});
```

### Event Propagation

1. **Capturing Phase**: Event đi từ document xuống target element
2. **Target Phase**: Event đạt đến target element
3. **Bubbling Phase**: Event nổi lên từ target element về document

---

# Attribute Reflection

## Reflected Attributes

Nhiều HTML attributes được "phản ánh" (reflected) trong DOM properties:

```javascript
// HTML: <input placeholder="Enter text" />
const input = document.querySelector('input');

// Cách 1: Sử dụng methods
input.getAttribute('placeholder'); // "Enter text"
input.setAttribute('placeholder', 'New text');

// Cách 2: Sử dụng reflected property (tự nhiên hơn)
input.placeholder; // "Enter text"
input.placeholder = 'New text';
```

### Boolean Attributes

```javascript
// HTML: <input type="checkbox" checked />
const checkbox = document.querySelector('input[type="checkbox"]');

checkbox.getAttribute('checked'); // "" (nếu checked) hoặc null
checkbox.checked; // true/false
```

---

# Tiêu Chuẩn DOM của W3C

_W3C (World Wide Web Consortium) là tổ chức quốc tế phát triển các tiêu chuẩn cho World Wide Web. W3C được thành lập bởi Tim Berners-Lee, người phát minh ra World Wide Web, với mục tiêu đảm bảo rằng các tiêu chuẩn web được phát triển một cách đồng nhất và có thể tương thích trên nhiều nền tảng và thiết bị khác nhau._

-   **Core DOM**: Mô hình chung cho tất cả các loại tài liệu.
-   **XML DOM**: Mô hình cho tài liệu XML.
-   **HTML DOM**: Mô hình cho tài liệu HTML.

### DOM Level Specifications

| DOM Level   | Năm  | Tính Năng Chính                          |
| ----------- | ---- | ---------------------------------------- |
| DOM Level 1 | 1998 | Core DOM, HTML DOM cơ bản                |
| DOM Level 2 | 2000 | Events, CSS manipulation, Range          |
| DOM Level 3 | 2004 | XPath, Keyboard events, Document loading |
| DOM Level 4 | 2015 | Selectors API, Mutation Observer         |

---

# Ví Dụ Thực Tế

## 1. Tạo Bảng HTML Động

```javascript
function createTable() {
	// Tạo các element
	const table = document.createElement('table');
	const tableBody = document.createElement('tbody');

	// Tạo các hàng và cột
	for (let i = 0; i < 3; i++) {
		const row = document.createElement('tr');

		for (let j = 0; j < 3; j++) {
			const cell = document.createElement('td');
			const cellText = document.createTextNode(`Row ${i}, Col ${j}`);
			cell.appendChild(cellText);
			row.appendChild(cell);
		}

		tableBody.appendChild(row);
	}

	// Ghép vào DOM
	table.appendChild(tableBody);
	document.body.appendChild(table);
	table.setAttribute('border', '1');
}
```

## 2. [Event Handling](../Events/README.md)

## 3. DOM Navigation và Manipulation

```javascript
// Tìm element và thao tác với siblings
const currentElement = document.querySelector('.current');
const nextElement = currentElement.nextElementSibling;
const previousElement = currentElement.previousElementSibling;
const parent = currentElement.parentElement;

// Thêm class cho tất cả children
const children = parent.children;
for (let child of children) {
	child.classList.add('processed');
}

// Sử dụng querySelector với selectors phức tạp
const specificElements = document.querySelectorAll('div.container > p:first-child');
```

---

# Luyện Tập

1.  **Thay đổi màu nền của một phần tử khi click vào nó.** [**lời giải**](./solves/B1.html)
2.  **Thêm một phần tử mới vào cuối danh sách.** [**lời giải**](./solves/B2.html)
3.  **Xóa một phần tử khỏi danh sách.** [**lời giải**](./solves/B3.html)
4.  **Thay đổi kích thước của một phần tử.** [**lời giải**](./solves/B4.html)
5.  **Hiển thị một thông báo khi chuột di chuyển qua một phần tử.** [**lời giải**](./solves/B5.html)
6.  **Hiển thị một thông báo khi một phần tử được click.** [**lời giải**](./solves/B6.html)

> _Danh sách bài giải ở đây [**solves**](./solves)_

## Các bài tập thú vị hơn (không có sẵn lời giải)

1. **Kéo thả ô từ vị trí này sang vị trí khác**
2. **Nhập thể 2 block và tăng kích thước**
3. **Tic-Tac-Toe**
4. **Image Gallery**

---

# Best Practices

## Performance Considerations

1. **Minimize DOM Queries**: Cache DOM references

```javascript
// Tốt
const element = document.getElementById('myElement');
element.style.color = 'red';
element.style.fontSize = '16px';

// Không tốt
document.getElementById('myElement').style.color = 'red';
document.getElementById('myElement').style.fontSize = '16px';
```
