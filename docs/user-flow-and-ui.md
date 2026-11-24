# Đặc tả Luồng người dùng (User Flow) & Giao diện (UI) – HTQLHTTT

## 1. Luồng người dùng (User Flows)

### UF-01: Đăng ký và Đăng nhập hệ thống (Gắn với US01)
- **Vai trò:** Sinh viên, Giảng viên, Quản trị viên (Admin)
- **Điều kiện tiên quyết:** Có kết nối mạng và truy cập được giao diện hệ thống.
- **Luồng chính:**
  1. Người dùng mở màn hình Đăng nhập/Đăng ký.
  2. Nếu chưa có tài khoản, người dùng chuyển sang form Đăng ký, nhập thông tin (họ tên, email/tên đăng nhập, mật khẩu, xác nhận mật khẩu) và nhấn **Đăng ký**; sau đó chuyển sang form Đăng nhập.
  3. Người dùng nhập tài khoản/email và mật khẩu, nhấn **Đăng nhập**.
  4. Hệ thống kiểm tra hợp lệ và xác thực thông tin, sau đó điều hướng đến trang chính phù hợp với vai trò.
- **Luồng ngoại lệ:**
  - Để trống hoặc sai định dạng email/mật khẩu: hiển thị thông báo lỗi ngay dưới trường nhập liệu.
  - Sai thông tin đăng nhập hoặc tài khoản chưa tồn tại: hiển thị thông báo lỗi rõ ràng, giữ nguyên dữ liệu đã nhập để người dùng chỉnh sửa.
  - Lỗi kết nối hoặc lỗi hệ thống: hiển thị thông báo lỗi, không làm mất dữ liệu đang nhập.

### UF-02: Phân quyền truy cập theo vai trò (Gắn với US02)
- **Vai trò:** Hệ thống & Quản trị viên / Giảng viên / Sinh viên
- **Điều kiện tiên quyết:** Người dùng đã đăng nhập thành công vào hệ thống.
- **Luồng chính:**
  1. Hệ thống xác định vai trò của tài khoản hiện tại (Sinh viên, Giảng viên hoặc Admin).
  2. Giao diện hiển thị menu chức năng và các nút thao tác tương ứng đúng quyền hạn của vai trò đó.
- **Luồng ngoại lệ:**
  - Người dùng cố tình truy cập đường dẫn hoặc thao tác ngoài phạm vi quyền: hệ thống chặn truy cập, hiển thị thông báo không có quyền hoặc chuyển hướng về trang phù hợp.

### UF-03: Quản lý Khóa học & Bài học của Giảng viên (Gắn với US03, US04)
- **Vai trò:** Giảng viên
- **Điều kiện tiên quyết:** Đã đăng nhập với vai trò Giảng viên và được cấp quyền quản lý khóa học.
- **Luồng chính:**
  1. Giảng viên truy cập khu vực **Quản lý khóa học**.
  2. Với khóa học (`US03`): giảng viên nhấn **Tạo khóa học** / **Sửa** / **Xóa**, nhập hoặc cập nhật thông tin khóa học (tên khóa học, mô tả, trạng thái) và lưu.
  3. Với bài học (`US04`): giảng viên mở chi tiết khóa học, chọn **Thêm bài học** / **Sửa** / **Xóa** (nội dung video/tài liệu đính kèm, thứ tự bài học) và lưu.
  4. Hệ thống cập nhật danh sách khóa học/bài học và hiển thị thông báo thành công.
- **Luồng ngoại lệ:**
  - Thiếu tên khóa học/bài học hoặc định dạng tài liệu/liên kết không hợp lệ: giữ lại dữ liệu trên form và hiển thị thông báo lỗi cụ thể.
  - Xóa khóa học/bài học: hiển thị hộp thoại xác nhận trước khi thực hiện xóa.

### UF-04: Xem khóa học, đăng ký tham gia và học bài (Gắn với US05)
- **Vai trò:** Sinh viên
- **Điều kiện tiên quyết:** Đã đăng nhập với vai trò Sinh viên.
- **Luồng chính:**
  1. Sinh viên xem danh sách khóa học khả dụng (có thể tìm kiếm hoặc lọc theo từ khóa).
  2. Sinh viên mở chi tiết khóa học và nhấn **Đăng ký tham gia**.
  3. Sau khi đăng ký thành công, sinh viên chọn bài học trong danh sách để xem video/tài liệu và theo dõi tiến độ học tập.
- **Luồng ngoại lệ:**
  - Chưa đăng ký khóa học hoặc khóa học chưa mở cho đăng ký: hiển thị thông báo trạng thái phù hợp hoặc yêu cầu đăng ký trước khi học bài.
  - Bài học chưa có nội dung hoặc lỗi tải video/tài liệu: hiển thị trạng thái trống nội dung hoặc thông báo lỗi tải tài liệu.

### UF-05: Tạo Quiz, làm bài có tính giờ và tự động chấm điểm (Gắn với US06, US07, US08)
- **Vai trò:** Giảng viên (tạo Quiz), Sinh viên (làm bài & xem kết quả)
- **Điều kiện tiên quyết:** Giảng viên đã có khóa học/bài học; Sinh viên đã tham gia khóa học có bài Quiz.
- **Luồng chính:**
  1. Giảng viên tạo bài Quiz trắc nghiệm gắn với khóa học/bài học, nhập câu hỏi, các phương án trả lời, đáp án đúng và thời gian làm bài (`US06`).
  2. Sinh viên mở bài Quiz, hệ thống khởi động **đồng hồ tính giờ** và cho phép chọn đáp án cho từng câu hỏi (`US07`).
  3. Sinh viên nhấn **Nộp bài** (hoặc hệ thống tự động nộp khi đồng hồ đếm ngược kết thúc).
  4. Hệ thống **tự động chấm điểm**, lưu kết quả vào hệ thống và hiển thị điểm số/chi tiết kết quả cho sinh viên (`US08`).
- **Luồng ngoại lệ:**
  - Hết thời gian làm bài: khóa thao tác làm tiếp và tự động nộp bài với các đáp án đã chọn.
  - Lỗi mạng hoặc lỗi hệ thống khi nộp bài: hiển thị thông báo lỗi rõ ràng và cho phép thử nộp lại/kiểm tra trạng thái lưu kết quả.

---

## 2. Đặc tả Giao diện (UI Specification)

### UI-01: Màn hình Đăng nhập / Đăng ký (Gắn với US01)
- **Mục đích:** Xác thực tài khoản người dùng và đăng ký tài khoản mới.
- **Bố cục:** Khung biểu mẫu ở giữa màn hình, hỗ trợ chuyển đổi giữa tab/chế độ Đăng nhập và Đăng ký.
- **Thành phần chính:** Ô nhập Email/Tài khoản (bắt buộc), ô nhập Mật khẩu (bắt buộc, có nút ẩn/hiện mật khẩu), ô nhập lại mật khẩu/họ tên (khi đăng ký), nút **Đăng nhập** / **Đăng ký**, liên kết chuyển đổi chế độ.

### UI-02: Trang tổng quan & Điều hướng theo vai trò (Gắn với US02)
- **Mục đích:** Điều hướng người dùng tới đúng các chức năng được phép theo vai trò.
- **Bố cục:** Thanh điều hướng trên/bên trái hiển thị tên người dùng, vai trò và danh sách menu; khu vực nội dung chính bên cạnh.
- **Thành phần chính:** Danh sách menu theo quyền (Sinh viên / Giảng viên / Admin), thông tin tài khoản, nút **Đăng xuất**.

### UI-03: Màn hình Quản lý Khóa học & Bài học (Gắn với US03, US04)
- **Mục đích:** Hỗ trợ Giảng viên tạo, sửa, xóa khóa học và quản lý danh sách bài học (video/tài liệu).
- **Bố cục:** Thanh công cụ phía trên (ô tìm kiếm, nút **Tạo khóa học**), bảng/danh sách khóa học và khu vực quản lý bài học của khóa học được chọn.
- **Thành phần chính:** Thông tin khóa học, danh sách bài học (video/tài liệu), các nút **Thêm / Sửa / Xóa**, form/modal nhập liệu và hộp thoại xác nhận xóa.

### UI-04: Màn hình Khám phá khóa học & Học bài (Gắn với US05)
- **Mục đích:** Hỗ trợ Sinh viên tìm kiếm, đăng ký khóa học và học bài (xem video/tài liệu).
- **Bố cục:** Danh sách khóa học dạng thẻ/bảng; khi học bài gồm khu vực hiển thị video/tài liệu chính và danh sách bài học bên cạnh/dưới.
- **Thành phần chính:** Thông tin khóa học, nút **Đăng ký tham gia**, danh sách bài học, khung xem video/tài liệu.

### UI-05: Màn hình Làm bài Quiz & Kết quả (Gắn với US06, US07, US08)
- **Mục đích:** Tạo bài Quiz (Giảng viên), làm bài trắc nghiệm có tính giờ (Sinh viên) và hiển thị điểm số tự động chấm.
- **Bố cục:** Thanh header hiển thị tên bài Quiz và **đồng hồ đếm ngược**, khu vực câu hỏi & đáp án ở giữa, nút **Nộp bài** và khung hiển thị điểm/kết quả sau khi nộp.
- **Thành phần chính:** Đồng hồ tính giờ, danh sách câu hỏi và lựa chọn đáp án, nút **Nộp bài**, bảng kết quả & điểm số.

### Trạng thái giao diện áp dụng chung
- **Empty (Trống dữ liệu):** Hiển thị thông báo thân thiện khi chưa có dữ liệu (chưa có khóa học, bài học, câu hỏi Quiz hoặc kết quả làm bài).
- **Loading (Đang tải):** Hiển thị chỉ báo đang tải khi lấy dữ liệu, lưu thay đổi hoặc chấm điểm.
- **Success (Thành công):** Hiển thị thông báo xác nhận rõ ràng sau khi thực hiện thành công thao tác.
- **Error (Lỗi):** Hiển thị thông báo lỗi dễ hiểu tại vị trí liên quan và giữ nguyên dữ liệu người dùng đã nhập.

---

## 3. Bảng ánh xạ Truy xuất (Traceability Matrix)

| Mã User Story | Tên chức năng | Mã User Flow | Mã / Màn hình UI | Giai đoạn dự kiến |
| :--- | :--- | :--- | :--- | :--- |
| `US01` | Đăng ký và Đăng nhập hệ thống | `UF-01` | `UI-01` – Đăng nhập / Đăng ký | Sprint 1 |
| `US02` | Phân quyền truy cập theo vai trò | `UF-02` | `UI-02` – Điều hướng & Trang chính theo vai trò | Sprint 1 |
| `US03` | Giảng viên tạo, sửa, xóa khóa học | `UF-03` | `UI-03` – Quản lý Khóa học & Bài học | Sprint 1 |
| `US04` | Giảng viên thêm, sửa, xóa bài học | `UF-03` | `UI-03` – Quản lý Khóa học & Bài học | Sprint 1 |
| `US05` | Sinh viên xem, đăng ký và học bài | `UF-04` | `UI-04` – Khám phá khóa học & Học bài | Sprint 1 |
| `US06` | Giảng viên tạo bài Quiz trắc nghiệm | `UF-05` | `UI-05` – Tạo / Làm bài Quiz & Kết quả | Sprint 1+ |
| `US07` | Sinh viên làm bài Quiz có tính giờ | `UF-05` | `UI-05` – Làm bài Quiz có tính giờ | Sprint 1+ |
| `US08` | Tự động chấm điểm và lưu kết quả | `UF-05` | `UI-05` – Kết quả & Điểm số Quiz | Sprint 1+ |
