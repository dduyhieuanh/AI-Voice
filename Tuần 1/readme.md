# Backend

## Khái niệm và ý nghĩa của Backend
Backend là phần mà người dùng không thể nhìn thấy được của một ứng dụng hay web nhưng đóng một vai trò quan trọng trong việc vận hành hoạt động của ứng dụng được diễn ra mượt mà. \
\
Có thể hiểu Backend là từ bên phía "máy chủ" của ứng dụng, chịu trách nhiệm xử lý dữ liệu, quản lý cơ sở dữ liệu, và đảm bảo mọi thứ hoạt động đúng cách để người dùng có thể tương tác với giao diện người dùng một cách dễ dàng.

## Kiến trúc của Backend
 ![kiến trúc của backend](https://topdev.vn/blog/wp-content/uploads/2022/06/back-end-hoat-dong-ra-sao.jpg)

Các bước hoạt động của Backend: 
1. **Nhận yêu cầu:** Backend nhận yêu cầu từ người dùng thông qua HTTP
2. **Xác thực và xử lý:** Kiểm tra thông tin đăng nhập và quyền truy cập. Sau đó, truy vấn cơ sở dữ liệu để lấy hoặc cập nhật dữ liệu.
3. **Giao Tiếp Với Các Dịch Vụ:** Tương tác với các vi dịch vụ và API bên thứ ba nếu cần.
4. **Xử Lý Logic:** Thực hiện các phép toán và quy trình theo yêu cầu của ứng dụng.
5. **Tạo Phản Hồi:** Tạo phản hồi dựa trên kết quả xử lý và gửi lại cho giao diện người dùng.
6. **Quản Lý Tải:** Sử dụng kỹ thuật như phân bổ tải và bộ nhớ đệm để xử lý nhiều yêu cầu đồng thời và tối ưu hóa hiệu suất.

# FastAPI

## Khái niệm
FastAPI là một framework web hiệu suất cao cho ngôn ngữ lập trình Python, chạy trên máy chủ web, được thiết kế để xây dựng các API nhanh chóng và mạnh mẽ. Nó kết hợp sức mạnh của Python với các tính năng hiện đại trong phát triển web để cung cấp hiệu suất tốt và tài liệu API tự động.
