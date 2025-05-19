# 🚦 BẤT ĐỒNG BỘ TRONG JAVASCRIPT (Asynchronous JavaScript)

Tài liệu này giúp bạn hiểu rõ về lập trình bất đồng bộ trong JavaScript, từ cơ bản đến nâng cao. Các kiến thức được phân tầng theo độ khó, giúp bạn dễ dàng tiếp cận và học tập.

---

## 1. Tổng quan về bất đồng bộ

-   **JavaScript là ngôn ngữ đơn luồng**: Chỉ thực hiện một tác vụ tại một thời điểm. Nếu phải chờ các tác vụ lâu (như gọi API, đọc file...), trang web sẽ bị "đóng băng".
-   **Lập trình bất đồng bộ** giúp JavaScript tiếp tục thực hiện các công việc khác trong khi chờ tác vụ dài hoàn thành, giúp ứng dụng mượt mà hơn.

---

## 2. Các kỹ thuật bất đồng bộ (Từ cơ bản đến nâng cao)

### 2.1. Callback (Hàm gọi lại)

-   **Khái niệm**: Hàm được truyền vào như một đối số và được gọi khi tác vụ hoàn thành.
-   **Ưu điểm**: Đơn giản, dễ hiểu cho các tác vụ nhỏ.
-   **Nhược điểm**: Dễ dẫn đến "callback hell" khi lồng nhiều callback, khó bảo trì.
-   📄 Xem chi tiết: [asynchronous/callback/README.md](callback/README.md)

---

### 2.2. Promise (Lời hứa)

-   **Khái niệm**: Đối tượng đại diện cho kết quả của một tác vụ bất đồng bộ trong tương lai.
-   **Ưu điểm**: Giúp mã dễ đọc hơn, tránh callback hell, quản lý lỗi tốt hơn với `.then()`, `.catch()`, `.finally()`.
-   **Nhược điểm**: Khi kết hợp nhiều Promise phức tạp, mã vẫn có thể khó hiểu.
-   📄 Xem chi tiết: [asynchronous/promises/README.md](promises/README.md)

---

### 2.3. Async/Await

-   **Khái niệm**: Cú pháp mới giúp viết mã bất đồng bộ trông giống như mã đồng bộ.
-   **Ưu điểm**: Đơn giản hóa mã, dễ đọc, dễ quản lý lỗi với `try/catch`, kết hợp tốt với Promise.
-   **Nhược điểm**: Chỉ sử dụng được với Promise.
-   📄 Xem chi tiết: [asynchronous/async_await/README.md](async_await/README.md)

---

## 3. Lời khuyên khi học

-   Hãy học theo thứ tự: Callback → Promise → Async/Await để hiểu rõ bản chất và sự phát triển của bất đồng bộ trong JavaScript.
-   Thực hành nhiều ví dụ để nắm vững cách hoạt động của từng kỹ thuật.
-   Đọc kỹ các README chi tiết trong từng thư mục để hiểu sâu hơn.

---

> **Đóng góp & chỉnh sửa:** Nếu bạn phát hiện lỗi hoặc muốn bổ sung nội dung, hãy tạo pull request hoặc liên hệ với nhóm tác giả.
