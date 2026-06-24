# BÁO CÁO TIẾN ĐỘ VÀ QUÁ TRÌNH THỰC HÀNH - GIT FOUNDATIONS

## 1. Thông tin học viên & Dự án
- **Khóa học:** Git Foundations (Microsoft Learn - GitHub Foundations)
- **Học viên:** Nguyễn Ngô Hoàng Vũ
- **Tên kho lưu trữ (Repository):** `git-safety-foundation`

---

## 2. Mô tả quá trình học tập
Lộ trình học tập được chia làm 2 giai đoạn chính dựa theo tài liệu Microsoft Learn:
- **Giai đoạn 1 (Cơ bản):** Tiếp cận các khái niệm cốt lõi của Git bao gồm quản lý mã nguồn cục bộ, làm việc với hệ thống lưu trữ đám mây GitHub, tìm hiểu cách hoạt động của mô hình GitHub Flow (Branching, Committing, Pull Request).
- **Giai đoạn 2 (Cộng tác nâng cao):** Học cách quản lý, phân quyền và bảo mật dự án. Thực hành các tình huống thực tế phức tạp như giải quyết xung đột mã nguồn (Conflict), quản lý lịch sử commit và thực hiện hoàn tác an toàn (Revert/Rollback).

---

## 3. Nhật ký thực hành chi tiết (Minh chứng đạt tiêu chuẩn đầu ra)

Tôi đã hoàn thành xuất sắc tất cả các điều kiện hoàn thành bắt buộc từ AKA Lab đề ra:

### 3.1. Số lượng Cam kết (Commits)
- **Yêu cầu:** Có tối thiểu 10 commit có ý nghĩa.
- **Kết quả thực tế:** Dự án đã tích lũy và ghi nhận thành công **14 - 16 Cam kết** gắn liền với tiến độ cập nhật nội dung qua từng giai đoạn.

### 3.2. Quản lý Nhánh (Branches)
- **Yêu cầu:** Có tối thiểu 3 branch thực hành.
- **Kết quả thực tế:** Hệ thống ghi nhận tôi đã khởi tạo và điều phối công việc thành công trên 3 nhánh riêng biệt:
  1. `chính` (main): Nhánh phân phối chính thức lưu trữ sản phẩm cuối cùng.
  2. `hồ sơ tính năng` (feature-profile): Nhánh phụ tạo ra nhằm phục vụ việc thêm tập tin `profile.md`.
  3. `nhánh-xung-đột`: Nhánh phụ dùng để cố ý thay đổi dữ liệu nhằm tạo bẫy xung đột hệ thống.

### 3.3. Yêu cầu kéo (Pull Requests)
- **Yêu cầu:** Có tối thiểu 2 pull request.
- **Kết quả thực tế:** Thực hiện mở và hợp nhất thành công **3 Pull Requests**:
  - **Pull Request #1:** Hợp nhất nhánh phụ `hồ sơ tính năng` vào nhánh `chính` thành công.
  - **Pull Request #2:** Hợp nhất `nhánh-xung-đột` vào nhánh `chính` sau khi đã tự sửa lỗi thủ công.
  - **Pull Request #3 (Revert):** Pull Request phục vụ mục đích hoàn tác, đảo ngược thay đổi của PR #2.

### 3.4. Xử lý Xung đột dữ liệu (Git Conflict)
- **Tình huống mô tả:** Khi gộp nhánh phụ vào nhánh chính tại Pull Request #2, hệ thống phát hiện cả 2 nhánh cùng chỉnh sửa tệp `README.md` với nội dung mâu thuẫn, dẫn đến việc không thể tự động gộp (Can't automatically merge).
- **Cách xử lý:** Tôi đã kích hoạt trình chỉnh sửa web **Resolve conflicts**, tiến hành xóa bỏ các thẻ đánh dấu xung đột (`<<<<<<<`, `=======`, `>>>>>>>`), giữ lại nội dung đồng nhất: *"Giải quyết xung đột: Thống nhất nội dung giữa nhánh chính và nhánh xung đột."* và tiến hành commit để hoàn thành việc gộp.

### 3.5. Xử lý Hoàn tác mã nguồn (Git Revert / Rollback)
- **Thực hành:** Sau khi gộp Pull Request #2, tôi đã chọn tính năng **Đảo ngược (Revert)** trực tiếp trên GitHub để mở PR #3, hoàn tác toàn bộ những thay đổi đã gộp một cách an toàn nhất mà không làm ảnh hưởng đến lịch sử kho chứa.

---

## 4. Tầm nhìn ứng dụng: "Tôi sẽ dùng Git như thế nào khi Vibe Code với AI?"

Khi bước vào giai đoạn **Vibe Code với AI** (sử dụng GitHub Copilot, Cursor, v.v.), AI hỗ trợ viết code rất nhanh, nhưng chính vì tốc độ đó nên Git sẽ trở thành **"chiếc phanh an toàn"** giúp kiểm soát dự án dựa trên 4 nguyên tắc:

1. **Git làm nút Hoàn tác (Undo) tối thượng:** Trước khi ra lệnh (Prompt) cho AI viết một tính năng lớn, tôi sẽ tạo một nhánh phụ. Nếu AI tạo ra mã lỗi hoặc "ảo tưởng" làm hỏng hệ thống, tôi có thể dùng Git để xóa sạch code lỗi và quay về trạng thái ổn định gần nhất một cách dễ dàng.
2. **Áp dụng Commit siêu nhỏ (Micro-commits):** Để kiểm soát AI, tôi không để AI viết một mạch quá dài. Cứ sau mỗi Prompt xử lý xong một hàm nhỏ, kiểm tra chạy ổn định là tôi sẽ thực hiện Commit ngay lập tức để đánh dấu cột mốc.
3. **Đóng vai trò người Duyệt mã (Code Reviewer):** AI đóng vai trò thợ gõ, còn tôi đóng vai trò kiểm soát. Trước khi lưu bất kỳ đoạn code nào của AI, tôi sẽ dùng lệnh `git diff` để kiểm tra kỹ lưỡng từng dòng chữ mà AI đã can thiệp.
4. **Tối ưu hóa Commit Message bằng AI:** Tôi sẽ tận dụng AI để phân tích các thay đổi của Git và viết hộ những thông điệp commit ngắn gọn, chuẩn chỉnh theo cấu trúc chuyên nghiệp (`feat:`, `fix:`, `docs:`).

---

## 5. Danh sách các lệnh Git đã sử dụng và làm chủ

Dưới đây là tập hợp các câu lệnh Git cốt lõi đã áp dụng thuần thục trong suốt dự án học tập này:

### 5.1. Nhóm lệnh khởi tạo và liên kết
- `git init`: Khởi tạo một kho lưu trữ Git cục bộ mới (Local Repository).
- `git clone <url>`: Sao chép toàn bộ mã nguồn và lịch sử của kho lưu trữ từ GitHub về máy cá nhân.
- `git remote add origin <url>`: Thiết lập liên kết giữa kho lưu trữ cục bộ với kho chứa từ xa trên GitHub.

### 5.2. Nhóm lệnh quản lý thay đổi hàng ngày
- `git status`: Kiểm tra trạng thái hiện tại của các file (File chưa theo dõi, file đã sửa hoặc đã đưa vào hàng chờ).
- `git add <tên_file>`: Đưa các thay đổi của tệp tin vào vùng đệm (Staging Area).
- `git commit -m "Thông điệp"`: Ghi lại vĩnh viễn ảnh chụp trạng thái mã nguồn vào lịch sử Git kèm mô tả chi tiết.

### 5.3. Nhóm lệnh quản lý Nhánh (Branch) & Hợp nhất
- `git branch <tên_nhánh>`: Khởi tạo một nhánh mới từ nhánh hiện tại.
- `git checkout <tên_nhánh>` (hoặc `git switch`): Di chuyển qua lại giữa các nhánh làm việc.
- `git merge <tên_nhánh_phụ>`: Hợp nhất lịch sử và code từ nhánh phụ vào nhánh chính.

### 5.4. Nhóm lệnh đồng bộ và Hoàn tác (Revert)
- `git push origin <tên_nhánh>`: Đẩy các commit mới từ máy cục bộ lên GitHub.
- `git pull origin <tên_nhánh>`: Kéo và cập nhật thay đổi mới nhất từ GitHub về máy.
- `git log`: Xem lại toàn bộ lịch sử danh sách các commit đã thực hiện trong quá khứ.
- `git revert <mã_commit>`: Tạo commit mới mang nội dung đối nghịch commit cũ nhằm hủy bỏ code lỗi một cách an toàn.

