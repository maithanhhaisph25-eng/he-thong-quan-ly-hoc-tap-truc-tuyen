# Hệ thống Quản lý Học tập Trực tuyến (Mini LMS)

Dự án xây dựng nền tảng học tập trực tuyến hỗ trợ Giảng viên quản lý khóa học, bài giảng, tạo bài kiểm tra trắc nghiệm (Quiz) và hỗ trợ Sinh viên học tập, làm bài kiểm tra trực tuyến với tính năng tự động chấm điểm.

---

## 👥 Thành viên nhóm (5 thành viên)

| STT | Họ và Tên | Mã sinh viên | Vai trò | Tài khoản GitHub |
| :-: | :--- | :--- | :--- | :--- |
| 1 | Mai Thanh Hải | 25S1020029 | Nhóm trưởng / Scrum Master / Fullstack |maithanhhaisph25@gmail.com |
| 2 | Trần Huỳnh Minh Thảo | 25S1020100 |Thành viên | minhthao20061002@gmail.com |
| 3 | Nguyễn Ngọc Nhật Quỳnh | 25S1020090 |Thành viên|nguyenquynh060606@gmail.com |
| 4 | Bùi Thị Bích Hợp | 25S1020041 | Thành viên | buihop19092007@gmail.com |
| 5 | Trần Thị Cẩm Nhung | 25S1080029 | Thành viên | tcamnhung93@gmail.com|

---

## 🔗 Liên kết quản lý dự án
* **Jira Board:** [Link Jira Space của nhóm](https://maithanhhaisph25.atlassian.net/jira/software/projects/HTQLHTTT/boards/3)

---

##  Công nghệ dự kiến (Tech Stack)
* **Quản lý công việc:** Jira 
* **Quản lý mã nguồn:** Git & GitHub
* **Công nghệ phát triển (Frontend / Backend / Database):** Đang thống nhất trong Sprint 0

---

## Phạm vi chức năng chính (Product Backlog)

### Epic 01: Xác thực & Phân quyền
* **US01:** Đăng ký và Đăng nhập hệ thống (Sinh viên, Giảng viên, Admin)
* **US02:** Phân quyền truy cập chức năng theo vai trò người dùng

### Epic 02: Quản lý Khóa học & Bài học
* **US03:** Giảng viên tạo, sửa, xóa khóa học
* **US04:** Giảng viên thêm, sửa, xóa bài học (video/tài liệu) vào khóa học
* **US05:** Sinh viên xem danh sách khóa học, đăng ký tham gia và học bài

### Epic 03: Quiz & Tự động chấm điểm
* **US06:** Giảng viên tạo bài Quiz trắc nghiệm gắn với khóa học/bài học
* **US07:** Sinh viên làm bài Quiz trực tuyến có tính giờ
* **US08:** Hệ thống tự động chấm điểm và lưu kết quả sau khi nộp bài

---

## 📂 Cấu trúc thư mục
* `docs/`: Chứa tài liệu phân tích thiết kế (Use Case, ERD, SRS, báo cáo Sprint).
* `src/`: Chứa mã nguồn ứng dụng (Frontend & Backend).
