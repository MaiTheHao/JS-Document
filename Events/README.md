# Tổng Quan về Event trong HTML và JavaScript

## Mục lục

1. [Khái niệm cơ bản về Event](#1-khái-niệm-cơ-bản-về-event)
2. [Phân loại các sự kiện](#2-phân-loại-các-sự-kiện)
3. [Cách thức xử lý sự kiện](#3-cách-thức-xử-lý-sự-kiện)
4. [Cơ chế lan truyền sự kiện](#4-cơ-chế-lan-truyền-sự-kiện)
5. [Quản lý và tối ưu hóa sự kiện](#5-quản-lý-và-tối-ưu-hóa-sự-kiện)
6. [Kỹ thuật nâng cao](#6-kỹ-thuật-nâng-cao)

---

## 1. Khái niệm cơ bản về Event

**Event (Sự kiện)** là các hành động hoặc tương tác mà người dùng thực hiện trên trang web, chẳng hạn như nhấp chuột, gõ phím, di chuyển chuột, hoặc các hành động tự động của trình duyệt như tải trang. JavaScript có thể lắng nghe và phản hồi lại các sự kiện này để tạo ra các tương tác động.

### Tại sao Event quan trọng?

-   Tạo tương tác người dùng
-   Xử lý dữ liệu form
-   Tạo hiệu ứng giao diện
-   Phản hồi hành vi người dùng

---

## 2. Phân loại các sự kiện

### 2.1 Sự kiện chuột (Mouse Events)

| Sự kiện       | Khi nào xảy ra                     |
| ------------- | ---------------------------------- |
| `click`       | Người dùng nhấp chuột trái         |
| `dblclick`    | Người dùng nhấp đúp chuột          |
| `mousedown`   | Nhấn nút chuột xuống (chưa thả)    |
| `mouseup`     | Thả nút chuột ra                   |
| `mouseover`   | Di chuột vào vùng phần tử          |
| `mouseout`    | Di chuột ra khỏi vùng phần tử      |
| `mousemove`   | Di chuyển chuột trong vùng phần tử |
| `contextmenu` | Nhấp chuột phải (menu ngữ cảnh)    |

### 2.2 Sự kiện bàn phím (Keyboard Events)

| Sự kiện    | Khi nào xảy ra               |
| ---------- | ---------------------------- |
| `keydown`  | Nhấn phím xuống              |
| `keyup`    | Thả phím ra                  |
| `keypress` | Nhấn phím ký tự (deprecated) |

### 2.3 Sự kiện form (Form Events)

| Sự kiện  | Khi nào xảy ra                      |
| -------- | ----------------------------------- |
| `submit` | Gửi form                            |
| `reset`  | Reset form về trạng thái ban đầu    |
| `change` | Giá trị input thay đổi và mất focus |
| `input`  | Giá trị input thay đổi ngay lập tức |
| `focus`  | Phần tử nhận focus                  |
| `blur`   | Phần tử mất focus                   |
| `select` | Chọn text trong input               |

### 2.4 Sự kiện tải trang (Page Events)

| Sự kiện            | Khi nào xảy ra                                   |
| ------------------ | ------------------------------------------------ |
| `load`             | Trang web hoặc phần tử tải hoàn tất              |
| `DOMContentLoaded` | DOM được xây dựng xong (không chờ CSS, hình ảnh) |
| `beforeunload`     | Trước khi rời khỏi trang                         |
| `unload`           | Khi rời khỏi trang                               |
| `resize`           | Thay đổi kích thước cửa sổ                       |
| `scroll`           | Cuộn trang                                       |

---

## 3. Cách thức xử lý sự kiện

### 3.1 Inline Event Handler (Không khuyến nghị)

```html
<button onclick="alert('Xin chào!')">Nhấp vào đây</button>
```

**Nhược điểm:**

-   Trộn lẫn HTML và JavaScript
-   Khó bảo trì khi dự án lớn
-   Không thể gán nhiều handler cho cùng một sự kiện

### 3.2 DOM Property Event Handler

```html
<button id="myButton">Nhấp vào đây</button>
<script>
  const button = document.getElementById('myButton');
  button.onclick = function () {
    alert('Đã nhấp button!');
  };
</script>
```

**Ưu điểm:**

-   Tách biệt HTML và JavaScript
-   Dễ đọc và hiểu

**Nhược điểm:**

-   Chỉ có thể gán một handler cho mỗi sự kiện

### 3.3 addEventListener() (Khuyến nghị sử dụng)

```html
<button id="myButton">Nhấp vào đây</button>
<script>
  const button = document.getElementById('myButton');

  button.addEventListener('click', function () {
    console.log('Handler thứ nhất');
  });

  button.addEventListener('click', function () {
    console.log('Handler thứ hai');
  });
</script>
```

**Ưu điểm:**

-   Có thể gán nhiều handler cho cùng một sự kiện
-   Hỗ trợ tùy chọn capture, once, passive
-   Có thể hủy bỏ bằng removeEventListener()
-   Cách tiếp cận hiện đại và linh hoạt

---

## 4. Cơ chế lan truyền sự kiện

### 4.1 Event Bubbling (Mặc định)

Sự kiện lan truyền từ phần tử con lên phần tử cha.

```html
<div id="outer">
  <div id="middle">
    <button id="inner">Nhấp vào đây</button>
  </div>
</div>

<script>
  document.getElementById('outer').addEventListener('click', () => {
    console.log('Outer div được nhấp');
  });

  document.getElementById('middle').addEventListener('click', () => {
    console.log('Middle div được nhấp');
  });

  document.getElementById('inner').addEventListener('click', () => {
    console.log('Button được nhấp');
  });
</script>
```

Kết quả khi nhấp button:

1. "Button được nhấp"
2. "Middle div được nhấp"
3. "Outer div được nhấp"

### 4.2 Event Capturing

Sự kiện lan truyền từ phần tử cha xuống phần tử con.

```javascript
// Sử dụng tham số thứ 3 là true hoặc { capture: true }
element.addEventListener('click', handler, true);
// hoặc
element.addEventListener('click', handler, { capture: true });
```

### 4.3 Ngăn chặn lan truyền

```javascript
button.addEventListener('click', function (event) {
  event.stopPropagation(); // Dừng lan truyền sự kiện
  console.log('Chỉ xử lý ở button');
});
```

### 4.4 Ngăn chặn hành vi mặc định

```javascript
link.addEventListener('click', function (event) {
  event.preventDefault(); // Ngăn hành vi mặc định (ví dụ: không theo link)
  console.log('Link không được theo');
});
```

---

## 5. Quản lý và tối ưu hóa sự kiện

### 5.1 Event Delegation (Ủy quyền sự kiện)

Thay vì gán sự kiện cho từng phần tử con, ta gán cho phần tử cha và kiểm tra target.

```html
<ul id="todoList">
  <li><button class="delete">Xóa</button> Công việc 1</li>
  <li><button class="delete">Xóa</button> Công việc 2</li>
  <li><button class="delete">Xóa</button> Công việc 3</li>
</ul>

<script>
  document.getElementById('todoList').addEventListener('click', function (event) {
    if (event.target.classList.contains('delete')) {
      event.target.parentElement.remove();
    }
  });
</script>
```

**Lợi ích:**

-   Giảm số lượng event listener
-   Tăng hiệu suất
-   Tự động xử lý cho các phần tử được thêm sau

### 5.2 Hủy bỏ Event Listener

```javascript
function handleClick() {
  console.log('Đã nhấp');
}

// Gán sự kiện
button.addEventListener('click', handleClick);

// Hủy sự kiện
button.removeEventListener('click', handleClick);
```

### 5.3 Sự kiện chỉ chạy một lần

```javascript
button.addEventListener(
  'click',
  function () {
    console.log('Chỉ chạy một lần');
  },
  { once: true }
);
```

---

## 6. Kỹ thuật nâng cao

### 6.1 Debouncing và Throttling

**Debouncing:** Trì hoãn thực thi cho đến khi không có sự kiện mới trong khoảng thời gian nhất định.

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function (...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => func.apply(this, args), delay);
  };
}

const searchInput = document.getElementById('search');
const debouncedSearch = debounce(function () {
  console.log('Tìm kiếm:', this.value);
}, 300);

searchInput.addEventListener('input', debouncedSearch);
```

**Throttling:** Giới hạn số lần thực thi trong một khoảng thời gian.

```javascript
function throttle(func, delay) {
  let lastCall = 0;
  return function (...args) {
    const now = Date.now();
    if (now - lastCall >= delay) {
      lastCall = now;
      func.apply(this, args);
    }
  };
}

const throttledScroll = throttle(function () {
  console.log('Đang cuộn');
}, 100);

window.addEventListener('scroll', throttledScroll);
```

### 6.2 Custom Events

```javascript
// Tạo sự kiện tùy chỉnh
const customEvent = new CustomEvent('myCustomEvent', {
  detail: { message: 'Đây là dữ liệu tùy chỉnh' },
});

// Lắng nghe sự kiện tùy chỉnh
document.addEventListener('myCustomEvent', function (event) {
  console.log(event.detail.message);
});

// Kích hoạt sự kiện
document.dispatchEvent(customEvent);
```

### 6.3 Async Event Handlers

```javascript
button.addEventListener('click', async function () {
  try {
    const response = await fetch('/api/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Lỗi:', error);
  }
});
```

---

## 7. Best Practices - Những Thói Quen Tốt Cho Dev Chuyên Nghiệp

### 7.1 Luôn dùng addEventListener() thay vì inline handlers

**Tại sao?** Giống như việc bạn không nên viết CSS inline trong HTML vậy. Code sạch sẽ, dễ maintain hơn nhiều.

```javascript
// ❌ Cách cũ - trộn lẫn HTML và JS
<button onclick='doSomething()'>Click me</button>;

// ✅ Cách đúng - tách biệt rõ ràng
const button = document.querySelector('#myButton');
button.addEventListener('click', doSomething);
```

**Ví dụ thực tế:** Bạn có một trang web bán hàng với 100 nút "Thêm vào giỏ". Nếu dùng inline, bạn phải copy-paste 100 lần. Còn với addEventListener, chỉ cần 1 đoạn code là xong!

### 7.2 Event Delegation - Ủy quyền thông minh

**Khái niệm đời thường:** Giống như việc bạn là quản lý quán cà phê. Thay vì phải hướng dẫn từng nhân viên mới về cách pha chế, bạn chỉ cần đưa ra quy định chung và để nhân viên cũ hướng dẫn người mới.

```html
<!-- Tưởng tượng đây là danh sách sản phẩm động -->
<div id="productList">
  <div class="product">
    <h3>iPhone 15</h3>
    <button class="buy-btn" data-product="iphone15">Mua ngay</button>
  </div>
  <div class="product">
    <h3>Samsung Galaxy</h3>
    <button class="buy-btn" data-product="samsung">Mua ngay</button>
  </div>
  <!-- Có thể có thêm nhiều sản phẩm được load bằng AJAX -->
</div>

<script>
  // ❌ Cách không hiệu quả - gán event cho từng button
  document.querySelectorAll('.buy-btn').forEach((btn) => {
    btn.addEventListener('click', handleBuy);
  });

  // ✅ Cách thông minh - chỉ gán 1 event cho container
  document.getElementById('productList').addEventListener('click', function (e) {
    if (e.target.classList.contains('buy-btn')) {
      const productId = e.target.dataset.product;
      addToCart(productId);
      showNotification(`Đã thêm ${productId} vào giỏ hàng!`);
    }
  });
</script>
```

**Lợi ích thực tế:**

-   Performance tốt hơn (ít event listeners hơn)
-   Tự động handle cho element được thêm sau
-   Code ngắn gọn, dễ maintain

### 7.3 Cleanup - Dọn dẹp event listeners

**Tại sao cần cleanup?** Giống như bạn thuê phòng trọ, khi chuyển đi phải trả phòng sạch sẽ. Không cleanup event có thể gây memory leak.

```javascript
class ShoppingCart {
  constructor() {
    this.handleAddToCart = this.handleAddToCart.bind(this);
    this.init();
  }

  init() {
    // Gán event khi khởi tạo
    document.addEventListener('click', this.handleAddToCart);
  }

  handleAddToCart(e) {
    if (e.target.classList.contains('add-to-cart')) {
      // Logic thêm vào giỏ hàng
      console.log('Đã thêm sản phẩm');
    }
  }

  destroy() {
    // ⭐ Quan trọng: cleanup khi không dùng nữa
    document.removeEventListener('click', this.handleAddToCart);
  }
}

// Sử dụng
const cart = new ShoppingCart();

// Khi chuyển trang hoặc component bị unmount
cart.destroy(); // Dọn dẹp sạch sẽ
```

### 7.4 Debouncing và Throttling - Tối ưu performance

**Debouncing - Đợi người dùng "ngừng" hành động:**

Giống như việc bạn đợi người bạn ngừng nói rồi mới phản hồi, thay vì chen ngang liên tục.

```javascript
// Tình huống thực tế: Search box tự động
function createSearchHandler() {
  let timeoutId;

  return function (e) {
    const keyword = e.target.value;

    // Hủy tìm kiếm trước đó nếu user vẫn đang gõ
    clearTimeout(timeoutId);

    // Đợi 300ms sau khi user ngừng gõ mới search
    timeoutId = setTimeout(() => {
      if (keyword.length >= 2) {
        searchProducts(keyword);
        console.log(`Đang tìm kiếm: ${keyword}`);
      }
    }, 300);
  };
}

const searchInput = document.getElementById('searchBox');
searchInput.addEventListener('input', createSearchHandler());
```

**Throttling - Giới hạn tần suất thực hiện:**

Giống như việc bạn chỉ cho phép nhân viên báo cáo mỗi 5 phút một lần, không phải lúc nào cũng báo.

```javascript
// Tình huống thực tế: Lazy loading khi scroll
function createScrollHandler() {
  let lastScrollTime = 0;
  const THROTTLE_DELAY = 100; // 100ms

  return function () {
    const now = Date.now();

    if (now - lastScrollTime >= THROTTLE_DELAY) {
      lastScrollTime = now;

      // Kiểm tra nếu scroll gần đáy trang thì load thêm sản phẩm
      const { scrollTop, scrollHeight, clientHeight } = document.documentElement;
      if (scrollTop + clientHeight >= scrollHeight - 1000) {
        loadMoreProducts();
        console.log('Loading thêm sản phẩm...');
      }
    }
  };
}

window.addEventListener('scroll', createScrollHandler());
```

### 7.5 Error Handling trong Events

**Luôn chuẩn bị cho trường hợp xấu nhất:**

```javascript
document.getElementById('paymentBtn').addEventListener('click', async function (e) {
  try {
    // Hiển thị loading
    e.target.disabled = true;
    e.target.textContent = 'Đang xử lý...';

    const response = await fetch('/api/payment', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ amount: 500000, product: 'iPhone 15' }),
    });

    if (!response.ok) {
      throw new Error(`Lỗi thanh toán: ${response.status}`);
    }

    const result = await response.json();

    // Thành công
    showSuccessMessage('Thanh toán thành công!');
    redirectToSuccessPage();
  } catch (error) {
    // Xử lý lỗi một cách thân thiện
    console.error('Chi tiết lỗi:', error);
    showErrorMessage('Có lỗi xảy ra khi thanh toán. Vui lòng thử lại!');
  } finally {
    // Luôn reset lại button
    e.target.disabled = false;
    e.target.textContent = 'Thanh toán';
  }
});
```

### 7.6 Accessibility - Làm web cho mọi người

**Hỗ trợ cả keyboard và screen reader:**

```javascript
// Làm cho custom dropdown có thể dùng bằng keyboard
const dropdown = document.getElementById('categoryDropdown');
const dropdownMenu = dropdown.querySelector('.dropdown-menu');

dropdown.addEventListener('keydown', function (e) {
  switch (e.key) {
    case 'Enter':
    case ' ': // Space
      e.preventDefault();
      toggleDropdown();
      break;

    case 'Escape':
      closeDropdown();
      dropdown.focus(); // Trả focus về trigger
      break;

    case 'ArrowDown':
      e.preventDefault();
      openDropdown();
      focusFirstMenuItem();
      break;
  }
});

// Focus management cho screen reader
function openDropdown() {
  dropdownMenu.classList.add('show');
  dropdown.setAttribute('aria-expanded', 'true');
}

function closeDropdown() {
  dropdownMenu.classList.remove('show');
  dropdown.setAttribute('aria-expanded', 'false');
}
```

## 8. Tóm Tắt - Takeaways

🎯 **Event là gì?** Những tương tác của user với trang web (click, scroll, type, v.v.)

🎯 **Cách tốt nhất?** Dùng `addEventListener()` với event delegation khi có thể

🎯 **Performance?** Áp dụng debounce/throttle cho events tần suất cao như scroll, resize

🎯 **Accessibility?** Hỗ trợ keyboard navigation và screen readers

🎯 **Debugging?** Dùng console.log và DevTools để track events

🎯 **Cleanup?** Luôn `removeEventListener()` khi không dùng nữa

**Nhớ nhé:** Event handling làm tốt = UX mượt mà = User happy = Boss happy = Lương tăng! 😄

---

_Hiểu và sử dụng đúng Events không chỉ giúp bạn tạo ra những trang web tương tác tốt, mà còn thể hiện tính chuyên nghiệp và khả năng tư duy logic trong lập trình._
