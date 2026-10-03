1. Phân tích và thiết kế cây thư mục
Để dự án CineBook Backend dễ quản lý, mã nguồn, hình ảnh người dùng và thông tin cấu hình nên được tách thành các thư mục riêng.
CineBook-Backend/
|
|-- src/
|   |-- controllers/
|   |-- models/
|   |-- routes/
|   |-- services/
|   |-- middlewares/
|   |-- app.py
|
|-- uploads/
|   |-- images/
|   |-- avatars/
|
|-- docs/
|   |-- README.md
|   |-- database.md
|
|-- config/
|   |-- .env
|
|-- tests/
|
|-- .gitignore
|
|-- requirements.txt
|
|-- README.md
2. Thiết kế giải pháp chặn lỗi
Đặt tên file mật khẩu
File chứa thông tin kết nối Database nên đặt tên:
.env
Ví dụ:
config/
|-- .env
File .env có thể chứa các thông tin cấu hình như:
DB_HOST=localhost
DB_NAME=cinebook
DB_USER=admin
DB_PASSWORD=********
Lưu ý: Đặt .env thành file ẩn chỉ giúp giảm khả năng vô tình nhìn thấy hoặc sao chép file. Đây không phải biện pháp bảo mật tuyệt đối. Không nên đưa .env lên Git hoặc chia sẻ công khai.
Cách ẩn .env trên Windows
Có thể thực hiện bằng giao diện:
Nhấp chuột phải vào file .env.
Chọn Properties.
Trong mục Attributes, tích Hidden.
Chọn Apply → OK.
Sau đó, nếu File Explorer đang tắt hiển thị file ẩn, .env sẽ không xuất hiện trong giao diện thông thường.
Có thể kiểm tra bằng:
File Explorer → View → Show → Hidden items
Ngoài ra, trong dự án nên có file:
.gitignore
và thêm:
.env
để tránh vô tình đưa file chứa mật khẩu lên Git.
3. Vai trò của các thư mục chính
Thư mục
Vai trò
src/
Chứa mã nguồn chính của Backend.
controllers/
Xử lý yêu cầu từ người dùng và trả kết quả.
models/
Định nghĩa dữ liệu và tương tác với Database.
routes/
Khai báo các API endpoint của hệ thống.
services/
Chứa các logic nghiệp vụ của ứng dụng.
middlewares/
Xử lý các bước trung gian như xác thực, kiểm tra quyền.
uploads/
Lưu các tệp người dùng tải lên, tách biệt khỏi mã nguồn.
docs/
Lưu tài liệu hướng dẫn và tài liệu kỹ thuật.
config/
Lưu các file cấu hình của hệ thống như .env.
tests/
Chứa mã kiểm thử cho Backend.

Kết luận
Cấu trúc này giúp CineBook tách rõ ba nhóm quan trọng: mã nguồn (src), dữ liệu người dùng (uploads) và cấu hình nhạy cảm (config/.env). Nhờ đó việc quản lý, bảo trì và bảo vệ dữ liệu sẽ rõ ràng hơn.


