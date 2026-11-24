# Báo cáo kiểm tra tính thống nhất tài liệu – Dự án HTQLHTTT (Sprint 0)

## 1. Bảng đối chiếu & phát hiện điểm cần đồng bộ

| Mã kiểm tra | Hạng mục đối chiếu | Nội dung hiện tại & Điểm cần rà soát | Quy ước chuẩn thống nhất đề xuất | Trạng thái |
| :--- | :--- | :--- | :--- | :--- |
| `CHK-01` | Tên & Mã dự án | `README.md` dùng tên "Hệ thống Quản lý Học tập Trực tuyến (Mini LMS)"; Jira dùng "Hệ thống quản lý học tập trực tuyến" và mã `HTQLHTTT`. | Thống nhất tên chính thức: **Hệ thống quản lý học tập trực tuyến (Mini LMS)**, mã dự án `HTQLHTTT`. | Đã đối chiếu |
| `CHK-02` | Phạm vi User Story (`US01` – `US08`) | `README.md` liệt kê `US01` đến `US08` chia 3 Epic (Xác thực & Phân quyền; Quản lý Khóa học & Bài học; Quiz & Tự động chấm điểm), nhưng chưa ghi rõ Priority, Story Points và Assignee từng US trong tài liệu. | Đồng bộ đầy đủ Priority, Story Points và Assignee của `US01`–`US08` giữa Jira Backlog và tài liệu đặc tả. | Cần nhóm chốt thêm |
| `CHK-03` | Phân tách Sprint 0 & Sprint 1 | Jira tách `Sprint 0 - Khởi tạo và Thiết kế` (`HTQLHTTT-17`–`HTQLHTTT-21`) với các `US` nằm ở `Backlog` chờ đưa vào Sprint 1. | Giữ rõ ranh giới: Sprint 0 chỉ làm khởi tạo, kiến trúc, Use Case, ERD, `README.md` & tài liệu nền tảng; Sprint 1 bắt đầu phát triển US. | Đã thống nhất |
| `CHK-04` | Vai trò người dùng (Role) | Các US nhắc tới Sinh viên, Giảng viên, Admin (và người dùng hệ thống). | Dùng thống nhất 3 vai trò: **Sinh viên**, **Giảng viên**, **Quản trị viên (Admin)**. | Đã chuẩn hóa |
| `CHK-05` | Tài liệu User Flow & UI | Thư mục `docs/` mới có `.gitkeep`, chưa có tài liệu mô tả luồng người dùng và đặc tả giao diện. | Bổ sung `docs/user-flow-and-ui.md` và liên kết trực tiếp từ `README.md`. | Đã bổ sung |
| `CHK-06` | Quy trình Git & Jira | Yêu cầu đẩy tài liệu/code lên nhánh `develop` (không sửa trực tiếp `main`) và cập nhật Jira Board (`To Do` -> `In Progress` -> `Done`). | Ghi rõ quy ước nhánh `develop` và quy trình cập nhật Jira trong `README.md`. | Đã bổ sung |
