# Callback Functions (Hàm gọi lại)

Là một hàm được truyền dưới dạng đối số cho một hàm khác và được thực thi (_gọi lại_) sau khi hàm đó hoàn thành công việc của mình. Nó cho phép bạn xác định hành vi sẽ xảy ra sau khi một nhiệm vụ hoàn tất, thường là không đồng bộ, hoặc khi một điều kiện cụ thể được thỏa mãn.

### **Đặc điểm chính của hàm callback:**

-   **Được truyền dưới dạng đối số**: Hàm callback thường được truyền dưới dạng đối số cho một hàm khác.
-   **Được thực thi sau**: Hàm nhận callback sẽ thực thi callback sau khi hoàn thành công việc của mình, thường là khi một tác vụ hoàn thành hoặc điều kiện được thỏa mãn.
-   **Thường được sử dụng trong các tác vụ không đồng bộ**: Hàm callback hay được sử dụng để xử lý các tác vụ không đồng bộ, như đọc file, xử lý sự kiện, hoặc gọi các yêu cầu mạng.
-   **Khuyến khích sử dụng arrow function cho callback**: Arrow function giúp giữ nguyên ngữ cảnh `this`, tránh lỗi và giảm nhu cầu dùng `_.bind(this)_`.

---

### **Ví dụ 1: Hàm Callback cơ bản (Đồng bộ)**

Trong ví dụ cơ bản, một hàm callback có thể được sử dụng đồng bộ để thực hiện một tác vụ sau khi một tác vụ khác hoàn tất:

```Javascript
// Hàm callback đơn giản
function greet(name) {
  console.log("Hello, " + name);
}

// Hàm nhận một hàm khác làm đối số
function processUserInput(callback) {
  var name = 'DuckMin';
  callback(name);  // Gọi hàm callback với tên người dùng
}

processUserInput(greet);  // Truyền hàm greet như một hàm callback
```

**Giải thích:**

-   `greet` là hàm callback.
-   `processUserInput` nhận một hàm làm đối số và gọi nó sau khi thực hiện công việc của mình.

---

### **Ví dụ 2: Hàm Callback không đồng bộ**

Hàm callback đặc biệt hữu ích để xử lý các tác vụ không đồng bộ, như đọc file hoặc gọi API. Trong JavaScript, hàm callback thường được sử dụng với các hàm như setTimeout(callback, ...), các trình xử lý sự kiện, hoặc các API.

```Javascript
const displayData = (data) => {
  console.log("Callback executed: " + data);
}

function fetchData(callback) {
  console.log("Fetching data...");
  const data = "Data fetched successfully";

  setTimeout(() => {
    callback(data);  // Gọi hàm callback sau khi dữ liệu được lấy
  }, 2000);  // Mô phỏng độ trễ 2 giây
}

// Gọi hàm fetchData và truyền displayData như một hàm callback
fetchData(displayData);
```

**Giải thích:**

-   `fetchData` mô phỏng việc lấy dữ liệu từ máy chủ không đồng bộ.
-   Sau khi dữ liệu được lấy (sau 2 giây), hàm callback `displayData` sẽ được gọi với dữ liệu đã lấy.
-   `displayData` là hàm callback được truyền vào `fetchData` và sẽ được thực thi khi dữ liệu đã sẵn sàng.

---

### **Ví dụ 3: Hàm Callback với xử lý lỗi (Thường thấy trong Node.js)**

Khi làm việc với các hàm callback trong _Node.js_ hoặc các môi trường không đồng bộ khác, thường có xử lý lỗi trong callback. Tham số đầu tiên của callback thường dành cho lỗi, và tham số thứ hai dành cho kết quả.

```Javascript
// Giả định có một database giả lập (bất đồng bộ)
const database = {
  1: { id: 1, name: "Alice" },
  2: { id: 2, name: "Bob" },
  get: (id) => {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        const user = this[id];
        user ? resolve(user) : reject(new Error("Không tìm thấy người dùng"));
      }, 1000);
    });
  }
};

// Hàm tìm người dùng bằng id kèm xử lý lỗi
async function findUserById(id, callback) {
  const response = {
    error: null,
    data: null
  }

  try {
    const user = await database.get(id);

    if(!user) {
      // Ném lỗi nếu không tìm thấy người dùng, ném lỗi sẽ được bắt bởi catch
      throw new Error("Không tìm thấy người dùng"); 
    }

    response.data = user;
  } catch (error) {
    // Bắt các lỗi dự kiến và không đoán trước được
    response.error = error;
  }

  // Gọi callback
  callback(response.error, response.data); 
}

// Hàm callback để xử lý kết quả
function handleData(error, data) {
  if (error) {
    console.error("Đã xảy ra lỗi:", error.message);
  } else {
    console.log("Dữ liệu người dùng:", data);
  }
}

// Gọi hàm findUserById với id và hàm callback
findUserById(1, handleData);
```

Giải thích:

-   Hàm callback `handleData` được gọi với hai tham số: `error` và `data`.
-   Nếu có lỗi, tham số đầu tiên chứa lỗi và tham số thứ hai là null. Nếu không có lỗi, tham số thứ hai chứa dữ liệu.
-   `findUserById` gọi `callback` với lỗi hoặc dữ liệu sau khi hoàn thành công việc của mình.

---

### **Ví dụ 4: Sử dụng Callback trong các trình xử lý sự kiện**

Callback cũng thường được sử dụng trong các trình xử lý sự kiện trong JavaScript, như khi xử lý sự kiện `click`:

```Javascript
// Thêm một trình xử lý sự kiện với hàm callback
document.getElementById('button').addEventListener('click', () => {
  alert("Button clicked! Hohoho.");
});
```

Giải thích:
Hàm được truyền vào `addEventListener` là một callback sẽ được thực thi khi sự kiện `click` xảy ra.

---

### **Lợi ích của hàm Callback:**

1. **Hành vi không đồng bộ**: Callbacks cho phép bạn xử lý các tác vụ không đồng bộ mà không làm tắc nghẽn luồng chính.
2. **Tính linh hoạt**: Bạn có thể truyền các hàm callback khác nhau cho các tác vụ khác nhau, làm cho mã dễ dàng mở rộng và tái sử dụng.
3. **Xử lý lỗi**: Với các callback theo kiểu "lỗi đầu tiên" (_error-first_), bạn có thể dễ dàng xử lý lỗi trong các tác vụ không đồng bộ.

### **Nhược điểm của hàm Callback:**

1. **Callback Hell:** Nếu có quá nhiều hàm callback lồng nhau, mã sẽ trở nên phức tạp và khó đọc, thường gọi là "_callback hell_" hoặc "_pyramid of doom_". Điều này có thể được giải quyết bằng cách sử dụng _Promises_ hoặc cú pháp _async_/_await_.
2. **Khó Debug:** Vì các callback thường thực thi không đồng bộ, việc theo dõi luồng chương trình có thể gặp khó khăn, làm cho việc gỡ lỗi trở nên phức tạp hơn.
3. **Vấn đề this trong function thường:** Khi truyền callback là "_function expression_", "_this_" có thể bị thay đổi ngoài ý muốn. Sử dụng "_arrow function_" giúp giữ nguyên "_this_", tránh lỗi và giảm nhu cầu dùng "_.bind(this)_".