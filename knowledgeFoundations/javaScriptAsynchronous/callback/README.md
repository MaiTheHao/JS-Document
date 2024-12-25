# Callback Functions (Hàm gọi lại)

Là một hàm được truyền dưới dạng đối số cho một hàm khác và được thực thi (gọi lại) sau khi hàm đó hoàn thành công việc của mình. Nó cho phép bạn xác định hành vi sẽ xảy ra sau khi một nhiệm vụ hoàn tất, thường là không đồng bộ, hoặc khi một điều kiện cụ thể được thỏa mãn.

### **Đặc điểm chính của hàm callback:**
- **Được truyền dưới dạng đối số**: Hàm callback thường được truyền dưới dạng đối số cho một hàm khác.
- **Được thực thi sau**: Hàm nhận callback sẽ thực thi callback sau khi hoàn thành công việc của mình, thường là khi một tác vụ hoàn thành hoặc điều kiện được thỏa mãn.
- **Thường được sử dụng trong các tác vụ không đồng bộ**: Hàm callback hay được sử dụng để xử lý các tác vụ không đồng bộ, như đọc file, xử lý sự kiện, hoặc gọi các yêu cầu mạng.

---

### **Ví dụ 1: Hàm Callback cơ bản (Đồng bộ)**

Trong ví dụ cơ bản, một hàm callback có thể được sử dụng đồng bộ để thực hiện một tác vụ sau khi một tác vụ khác hoàn tất:

```javascript
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


**Giải thích:**
_greet_ là hàm callback.
_processUserInput_ nhận một hàm làm đối số và gọi nó sau khi thực hiện công việc của mình.

**Ví dụ 2:** **_Hàm Callback không đồng bộ_**
Hàm callback đặc biệt hữu ích để xử lý các tác vụ không đồng bộ, như đọc file hoặc gọi API. Trong JavaScript, hàm callback thường được sử dụng với các hàm như setTimeout, các trình xử lý sự kiện, hoặc các API.

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

**Giải thích:**
_fetchData_ mô phỏng việc lấy dữ liệu từ máy chủ không đồng bộ.
Sau khi dữ liệu được lấy (sau 2 giây), hàm callback _displayData_ sẽ được gọi với dữ liệu đã lấy.

**Ví dụ 3: _Hàm Callback với xử lý lỗi (Thường thấy trong Node.js)_**
Khi làm việc với các hàm callback trong Node.js hoặc các môi trường không đồng bộ khác, thường có xử lý lỗi trong callback. Tham số đầu tiên của callback thường dành cho lỗi, và tham số thứ hai dành cho kết quả.
