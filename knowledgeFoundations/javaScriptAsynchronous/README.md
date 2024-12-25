# Asynchronous JavaScript

JavaScript là một ngôn ngữ đơn luồng, có nghĩa là nó chỉ có thể thực hiện một tác vụ tại một thời điểm. Điều này khá đơn giản nhưng lại gây vấn đề khi bạn cần thực hiện những công việc tốn thời gian, như gọi dữ liệu từ một API. Nếu JavaScript phải chờ xong tác vụ đó mới làm việc khác, trang web của bạn sẽ "_đóng băng_" và không phản hồi.

Để giải quyết vấn đề này, asynchronous JavaScript (*lập trình bất đồng bộ*) ra đời. Nó cho phép JavaScript tiếp tục làm các công việc khác trong khi chờ đợi các tác vụ dài hoàn thành, thay vì "đứng hình".

Các kỹ thuật như _callbacks_, _promises_ và _async_/*await* giúp bạn làm việc này. Ví dụ, *callbacks* là các hàm được gọi khi tác vụ xong, *promises* giúp bạn quản lý kết quả của các tác vụ chờ đợi, còn _async_/*await* giúp mã dễ đọc hơn khi xử lý các tác vụ bất đồng bộ. Nhờ có asynchronous, bạn có thể gửi yêu cầu lấy dữ liệu mà không làm ứng dụng bị "*đóng băng*", mang lại trải nghiệm mượt mà cho người dùng.
