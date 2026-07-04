# Hướng dẫn quay Video Demo submit Meta App Review (Internal CLI Tool)

Vì ứng dụng của bạn (**Quản Trị Page**) là một công cụ dòng lệnh (CLI - Command Line Interface) chạy local dưới dạng script Python, Meta Reviewer sẽ rất dễ reject nếu không hiểu cách vận hành. 

Bạn cần quay một video dài **từ 1.5 đến 3 phút** thể hiện rõ luồng hoạt động từ cấu hình -> chạy lệnh -> kết quả trên Facebook. Dưới đây là kịch bản chi tiết từng bước.

---

## 🎥 Yêu cầu kỹ thuật của video
- **Độ phân giải**: Tối thiểu 1080p, rõ nét chữ trên terminal.
- **Định dạng**: `.mp4`, `.mov`.
- **Dung lượng**: Dưới 100MB (theo giới hạn của Meta).
- **Ngôn ngữ**: Sử dụng tiếng Anh cho văn bản hiển thị (hoặc thuyết minh tiếng Anh/chú thích chữ tiếng Anh trong video).
- **Bảo mật**: **Tuyệt đối không để lộ đầy đủ Access Token**. Hãy che hoặc làm mờ token trong file `.env` trước khi quay, chỉ để lộ vài ký tự đầu và cuối.

---

## 🎬 Kịch bản quay Video (3 Phần chính)

### Phần 1: Chứng minh quyền sở hữu & Thiết lập App (30 giây đầu)
1. Mở trình duyệt, truy cập trang **Meta for Developers** -> Dashboard ứng dụng **"Quản Trị Page"** (App ID: `1477228617423402`).
2. Click vào **App Settings (Cài đặt) -> Basic (Thông tin cơ bản)**:
   - Cho reviewer thấy bạn đã điền link Privacy Policy URL (link GitHub Pages).
3. Click vào **App Roles (Vai trò ứng dụng)**:
   - Cho reviewer thấy tài khoản cá nhân của bạn đang là **Administrator** (Quản trị viên) của app này.
4. Mở tab Facebook Page (ví dụ: `ucviet-cute` hoặc page test của bạn) trên trình duyệt để thấy trạng thái trang hiện tại (chưa có bài đăng mới).

### Phần 2: Thực thi lệnh đăng bài trên Terminal (60 giây tiếp theo)
1. Mở công cụ dòng lệnh (Terminal/VS Code) lên.
2. Mở file `.env` chứa token của bạn, chứng minh cấu hình đang nằm ở local:
   - *Lưu ý*: Chỉ mở lướt qua hoặc che/bôi mờ token. Giải thích bằng chú thích chữ (Subtitle) trên video: *"Environment variables are stored locally on the administrator's secure machine."*
3. Chạy thử lệnh tạo bài viết lên lịch đăng (Scheduled Post).
   * **Lệnh chạy đăng bài kèm ảnh**:
     ```powershell
     uv run python schedule_post.py post-scheduled --page ucviet-cute --message "Meta App Review Test Post - Scheduled content" --image drafts/ucviet-cute/test.jpg --time "[Thời gian sau 15 phút, ví dụ: 2026-07-04T19:30:00+07:00]"
     ```
4. Chỉ vào terminal cho reviewer thấy kết quả thành công trả về dạng JSON từ Meta API:
   - `✓ Scheduled! id=xxxx_xxxx` (Cho thấy ID bài viết được tạo thành công).

### Phần 3: Xác minh kết quả trên Facebook Page (30 giây cuối)
1. Quay lại trình duyệt đang mở trang Facebook Page.
2. Truy cập vào **Meta Business Suite** -> mục **Planner (Lịch trình)** hoặc **Content (Nội dung) -> Scheduled (Đã lên lịch)**.
3. Nhấn **F5 (Reload)** trang.
4. Cho reviewer thấy bài viết bạn vừa chạy lệnh ở Phần 2 đã xuất hiện đúng trong danh sách bài viết đã lên lịch (Scheduled posts), kèm đúng hình ảnh và nội dung `"Meta App Review Test Post..."`.
5. Kết thúc video.

---

## 📝 Bản dịch Tiếng Anh (Dùng làm phụ đề hoặc Script nói)
Nếu bạn lồng tiếng hoặc làm phụ đề (Subtitles) chèn vào video, hãy dùng mẫu dưới đây:

* **Mở đầu:**
  > *"Hello Meta App Review team. This is a demo of the 'Quản Trị Page' application, which is an internal CLI tool used by the administrator to schedule and publish posts on our managed Facebook pages."*
  > (Xin chào đội ngũ xét duyệt Meta. Đây là video demo của app Quản Trị Page, một công cụ dòng lệnh nội bộ được admin dùng để lên lịch và đăng bài trên các page quản trị.)

* **Khi show cấu hình:**
  > *"The tool runs locally. Page access tokens are securely loaded from local environment variables."*
  > (Công cụ chạy ở local. Các page access token được load an toàn từ biến môi trường cục bộ.)

* **Khi chạy lệnh terminal:**
  > *"Now, we will execute the Python script to schedule a post with an image and text to our page."*
  > (Bây giờ chúng tôi sẽ chạy script Python để lên lịch bài viết gồm ảnh và chữ lên trang.)

* **Khi xác minh thành công:**
  > *"The post has been successfully scheduled. We can verify it directly in the Meta Business Suite Planner. As you can see, the post is now scheduled with the correct content. Thank you."*
  > (Bài đăng đã được lên lịch thành công. Chúng ta có thể kiểm tra trực tiếp trong lịch trình Meta Business Suite. Như bạn thấy, bài đăng đã ở trạng thái lên lịch với đúng nội dung. Xin cảm ơn.)
