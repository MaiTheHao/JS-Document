# Promise functions (Hàm hứa)

1. **Giới thiệu về Promise**

Trong JavaScript, khi thực hiện các tác vụ bất đồng bộ (*asynchronous tasks*), như việc gọi API, đọc file, hoặc xử lý sự kiện mạng, chương trình thường sẽ không chờ đợi các tác vụ này hoàn thành trước khi tiếp tục thực thi các câu lệnh tiếp theo. Điều này có thể gây ra vấn đề khó theo dõi khi làm việc với nhiều tác vụ bất đồng bộ lồng nhau. Chính vì vậy, Promise ra đời để giải quyết vấn đề này, giúp việc xử lý các tác vụ bất đồng bộ trở nên dễ dàng và trực quan hơn.

*Promise* là một đối tượng đại diện cho kết quả của một tác vụ bất đồng bộ sẽ có trong tương lai. Nó có thể ở một trong ba trạng thái:
- **Pending** (*Đang chờ*): Trạng thái ban đầu, khi Promise chưa được giải quyết.
- **Fulfilled** (*Hoàn thành*): Trạng thái khi Promise hoàn thành thành công.
- **Rejected** (*Từ chối*): Trạng thái khi có lỗi xảy ra trong quá trình thực thi.
Khi một Promise đã được giải quyết (fulfilled hoặc rejected), bạn có thể sử dụng các phương thức như then(), catch() để xử lý kết quả hoặc lỗi.

2. *Cấu trúc của Promise*
Một Promise được tạo ra thông qua cú pháp:

``` Javascript
let promise = new Promise(function(resolve, reject) {
  // Thực hiện một tác vụ bất đồng bộ (ví dụ gọi API, đọc file...)
  if (/* thành công */) {
    resolve(result);  // Gọi resolve khi thành công
  } else {
    reject(error);  // Gọi reject khi có lỗi
  }
});
```

- **resolve:** Hàm này được gọi khi tác vụ bất đồng bộ hoàn thành thành công và trả về kết quả.
- **reject:** Hàm này được gọi khi có lỗi xảy ra trong quá trình thực thi.

---

# Các phương thức cơ bản của Promise

1. ### **then()**

Phương thức ```then()``` được sử dụng để chỉ định hàm callback sẽ được gọi khi Promise hoàn thành thành công (*fulfilled*). Nó nhận hai tham số:

- Tham số 1 (*resolve_Handler*): Hàm sẽ được gọi khi Promise được giải quyết thành công.
- Tham số 2 (*reject_Handler*): Hàm sẽ được gọi khi Promise bị lỗi (tuy nhiên, tham số này là tùy chọn).

```Javascript
promise.then(resolveHandler, rejectHandler);
```

Ví dụ sử dụng ```then()```:

``` Javascript
let promise = new Promise(function(resolve, reject) {
  let success = true;
  if(success) {
    resolve("Tác vụ thành công!");
  } else {
    reject("Có lỗi xảy ra!");
  }
});

promise.then(function(result) {
  console.log(result);  // In ra "Tác vụ thành công!"
}).catch(function(error) {
  console.log(error);  // Nếu có lỗi xảy ra, in ra lỗi
});
```

Trong ví dụ trên:
- ```then()``` được gọi khi Promise thành công, và kết quả được hiển thị qua `console.log()`.
- Nếu có lỗi xảy ra, phương thức `catch()` sẽ được gọi.
