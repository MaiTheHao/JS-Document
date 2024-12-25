# Callback Functions (Hàm gọi lại)

Là một hàm được truyền dưới dạng đối số cho một hàm khác và được thực thi (gọi lại) sau khi hàm đó hoàn thành công việc của mình. Nó cho phép bạn xác định hành vi sẽ xảy ra sau khi một nhiệm vụ hoàn tất, thường là không đồng bộ, hoặc khi một điều kiện cụ thể được thỏa mãn.

### **Đặc điểm chính của hàm callback:**
- **Được truyền dưới dạng đối số**: Hàm callback thường được truyền dưới dạng đối số cho một hàm khác.
- **Được thực thi sau**: Hàm nhận callback sẽ thực thi callback sau khi hoàn thành công việc của mình, thường là khi một tác vụ hoàn thành hoặc điều kiện được thỏa mãn.
- **Thường được sử dụng trong các tác vụ không đồng bộ**: Hàm callback hay được sử dụng để xử lý các tác vụ không đồng bộ, như đọc file, xử lý sự kiện, hoặc gọi các yêu cầu mạng.

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
- _greet_ là hàm callback.
- _processUserInput_ nhận một hàm làm đối số và gọi nó sau khi thực hiện công việc của mình.

---

### **Ví dụ 2: _Hàm Callback không đồng bộ_**
Hàm callback đặc biệt hữu ích để xử lý các tác vụ không đồng bộ, như đọc file hoặc gọi API. Trong JavaScript, hàm callback thường được sử dụng với các hàm như setTimeout, các trình xử lý sự kiện, hoặc các API.

```Javascript
function fetchData(callback) {
  console.log("Fetching data...");
  setTimeout(function() {
    const data = "Data fetched successfully";
    callback(data);  // Gọi hàm callback sau khi dữ liệu được lấy
  }, 2000);  // Mô phỏng độ trễ 2 giây
}

function displayData(data) {
  console.log("Callback executed: " + data);
}

// Gọi hàm fetchData và truyền displayData như một hàm callback
fetchData(displayData);
```

**Giải thích:**
- _fetchData_ mô phỏng việc lấy dữ liệu từ máy chủ không đồng bộ.
- Sau khi dữ liệu được lấy (sau 2 giây), hàm callback _displayData_ sẽ được gọi với dữ liệu đã lấy.

---

### **Ví dụ 3: _Hàm Callback với xử lý lỗi (Thường thấy trong Node.js)_**
Khi làm việc với các hàm callback trong Node.js hoặc các môi trường không đồng bộ khác, thường có xử lý lỗi trong callback. Tham số đầu tiên của callback thường dành cho lỗi, và tham số thứ hai dành cho kết quả.

```Javascript
function fetchDataWithErrorHandling(callback) {
  setTimeout(function() {
    const error = null;
    const data = "Fetched data successfully";
    
    if (error) {
      callback(error, null);  // Gọi hàm callback với lỗi là tham số đầu tiên
    } else {
      callback(null, data);  // Gọi hàm callback với null là lỗi và dữ liệu là tham số thứ hai
    }
  }, 2000);
}

function handleData(error, data) {
  if (error) {
    console.log("Error occurred: " + error);
  } else {
    console.log("Data received: " + data);
  }
}

fetchDataWithErrorHandling(handleData);
```

Giải thích:
- Hàm callback _handleData_ được gọi với hai tham số: _error_ và _data_.
- Nếu có lỗi, tham số đầu tiên chứa lỗi và tham số thứ hai là null. Nếu không có lỗi, tham số thứ hai chứa dữ liệu.

---

### **Ví dụ 4: _Sử dụng Callback trong các trình xử lý sự kiện_**
Callback cũng thường được sử dụng trong các trình xử lý sự kiện trong JavaScript, như khi xử lý sự kiện click:

```Javascript
// Thêm một trình xử lý sự kiện với hàm callback
document.getElementById('button').addEventListener('click', function() {
  alert("Button clicked!");
});
```
Giải thích:
Hàm được truyền vào addEventListener là một callback sẽ được thực thi khi sự kiện "click" xảy ra.

---

### **Lợi ích của hàm Callback:**

1. **Hành vi không đồng bộ**: Callbacks cho phép bạn xử lý các tác vụ không đồng bộ mà không làm tắc nghẽn luồng chính.
2. **Tính linh hoạt**: Bạn có thể truyền các hàm callback khác nhau cho các tác vụ khác nhau, làm cho mã trở nên dễ dàng mở rộng và tái sử dụng.
3. **Xử lý lỗi**: Với các callback theo kiểu "lỗi đầu tiên" (error-first), bạn có thể dễ dàng xử lý lỗi trong các tác vụ không đồng bộ.
