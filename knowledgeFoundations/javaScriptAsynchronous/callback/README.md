******Callback Functions****** (Hàm gọi lại)

Là một hàm được truyền dưới dạng đối số cho một hàm khác và được thực thi (gọi lại) sau khi hàm đó hoàn thành công việc của mình. Nó cho phép bạn xác định hành vi sẽ xảy ra sau khi một nhiệm vụ hoàn tất, thường là không đồng bộ, hoặc khi một điều kiện cụ thể được thỏa mãn.

**Đặc điểm chính của hàm callback:**

- Được truyền dưới dạng đối số: Hàm callback thường được truyền dưới dạng đối số cho một hàm khác.
- Được thực thi sau: Hàm nhận callback sẽ thực thi callback sau khi hoàn thành công việc của mình, thường là khi một tác vụ hoàn thành hoặc điều kiện được thỏa mãn.
- Thường được sử dụng trong các tác vụ không đồng bộ: Hàm callback hay được sử dụng để xử lý các tác vụ không đồng bộ, như đọc file, xử lý sự kiện, hoặc gọi các yêu cầu mạng.
**Ví dụ 1:** Hàm Callback cơ bản (Đồng bộ)
Trong ví dụ cơ bản, một hàm callback có thể được sử dụng đồng bộ để thực hiện một tác vụ sau khi một tác vụ khác hoàn tất.

// Hàm callback đơn giản
function greet(name) {
console.log("Hello, " + name);
}
// Hàm nhận một hàm khác làm đối số
function processUserInput(callback) {
var name = 'Alice'; 
callback(name);  // Gọi hàm callback với tên người dùng
}
processUserInput(greet);  // Truyền hàm greet như một hàm callback
