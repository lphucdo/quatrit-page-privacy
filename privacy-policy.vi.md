---
title: "Chính sách bảo mật — Quản Trị Page"
app_name: "Quản Trị Page"
app_id: "1477228617423402"
version: 1.0
effective_date: 2026-07-04
last_updated: 2026-07-04
language: vi
target_audience: "Review nội bộ trước khi deploy"
status: draft
---

# Chính sách bảo mật — Quản Trị Page

> 📌 **Trạng thái**: BẢN NHÁP — chưa đăng công khai.
> Trước khi a upload lên hosting và submit cho Meta:
> - Điền email liên hệ thật ở mục 10 (hiện: `lamdo9@icloud.com`)
> - Review từng section một
> - Xem file `DEPLOY-CHECKLIST.md` để biết checklist trước khi deploy
> - Bản English ở file `privacy-policy.en.md` cho Meta reviewer


---

## 1. Tổng quan

**"Quản Trị Page"** (App ID: `1477228617423402`, loại Business) là công cụ quản lý nội dung cho Facebook Pages, được phát triển và vận hành bởi cá nhân **Phúc Lâm**.

Chính sách bảo mật này giải thích:
- Dữ liệu nào được thu thập khi a sử dụng app
- Cách dữ liệu được sử dụng và bảo vệ
- Quyền của a với dữ liệu của mình

App được thiết kế với nguyên tắc **thu thập tối thiểu** — chỉ lấy đúng những gì cần để vận hành tính năng chính (lên lịch và đăng bài viết trên các Facebook Pages).

## 2. Dữ liệu chúng tôi thu thập

### 2.1 Khi a đăng nhập bằng Facebook

| Dữ liệu | Mục đích | Bắt buộc |
|---------|----------|----------|
| **Page Access Token** | Cho phép app gọi Graph API thay mặt a để publish/schedule bài viết | ✅ Có |
| **Danh sách Pages** (id, tên, danh mục) | Hiển thị pages a quản trị để chọn đăng | ✅ Có |
| **Tên + avatar Facebook** | Xác minh danh tính admin | ✅ Có |

Dữ liệu này chỉ được truyền từ Meta → thiết bị của a qua Graph API theo scope mà a đã approve. App không can thiệp vào quá trình này.

### 2.2 Khi a sử dụng app

| Dữ liệu | Mô tả | Lưu ở đâu |
|---------|--------|-----------|
| **Caption text** | Văn bản a nhập | File Markdown local + asset folder |
| **Ảnh / Video** | Media a upload để đăng | File local trong folder drafts |
| **Lịch đăng** | Thời gian + trạng thái (draft/scheduled/posted) | Frontmatter trong file Markdown |
| **FB post ID sau đăng** | ID do Meta trả về | Trong posted-log để tracking |

### 2.3 Logs kỹ thuật

- **API errors**: lỗi response từ Meta API (status code + message) → file log cục bộ
- **Thời gian phản hồi**: dùng để debug performance
- **IP local**: chỉ dùng cho rate-limit self-protection, không gửi ra ngoài

### 2.4 ❌ Chúng tôi KHÔNG thu thập

- Thông tin cá nhân (PII) của **người theo dõi** page của a
- Tin nhắn riêng tư trên Facebook
- Comments hoặc nội dung user-generated từ bài viết
- Cookies, browser fingerprint, device ID
- Dữ liệu vị trí chính xác (GPS)
- Thông tin thiết bị chi tiết

## 3. Cách chúng tôi sử dụng dữ liệu

Dữ liệu của a chỉ được sử dụng cho các mục đích sau:

| Mục đích | Cần dữ liệu nào | Loại hoạt động |
|---------|-----------------|----------------|
| ✅ **Lên lịch và đăng bài viết** | Token + caption + media + lịch | Gọi Graph API theo lịch a đã đặt |
| ✅ **Quản lý nhiều Pages** | Danh sách Pages + ID | Hiển thị trong UI app |
| ✅ **Phân tích hiệu quả** | Reach, engagement (từ Meta API) | Hiển thị metrics cho admin |
| ✅ **Hỗ trợ kỹ thuật** | Logs lỗi | Debug khi API call fail |

### Dữ liệu KHÔNG được dùng để:

- ❌ Huấn luyện AI / machine learning
- ❌ Bán, cho thuê hoặc chia sẻ với bên thứ ba
- ❌ Tạo hồ sơ hành vi người dùng để quảng cáo
- ❌ Tạo nội dung **tự động** mà admin không yêu cầu (chống spam)

## 4. Chia sẻ với bên thứ ba

Dữ liệu của a chỉ được chia sẻ với **Meta Platforms (Facebook, Inc.)** — nhà cung cấp Graph API — theo đúng phạm vi permission mà a đã cấp.

Chúng tôi KHÔNG chia sẻ với bất kỳ bên thứ ba nào khác, bao gồm:

- ❌ Dịch vụ analytics (Google Analytics, Mixpanel, Amplitude, Facebook Pixel, etc.)
- ❌ Cloud storage công cộng (AWS, GCP, Azure — ngoại trừ để gọi Meta API)
- ❌ Nhà quảng cáo, ad networks, data brokers
- ❌ Bất kỳ service nào khác

App **không thuộc nhóm "spyware / surveillance"** và không theo dõi người dùng ngoài scope cho phép.

## 5. Lưu trữ và bảo mật

### 5.1 Nơi lưu trữ

| Loại dữ liệu | Nơi lưu | Bảo mật |
|--------------|---------|---------|
| Page Access Token | File `.env` local (encrypted at rest) | Quyền truy cập hạn chế (chmod 600) |
| Caption / ảnh / video | Folder `drafts/` local | Không sync cloud tự động |
| Posted-log | File `.posted-log.jsonl` local | Không sync cloud tự động |
| Logs kỹ thuật | File `/tmp/` local | Tự xóa sau 24h |

**Không có database trên cloud.** Mọi thứ chạy trên thiết bị cá nhân của admin. Không có backend server từ xa.

### 5.2 Bảo mật

- ✅ HTTPS cho mọi giao tiếp với Meta API
- ✅ Page Access Token không bao giờ được ghi vào log hoặc commit git
- ✅ Token có thể thu hồi ngay lập tức qua Meta Settings → Business Integrations
- ✅ App không lưu password — chỉ dùng Meta OAuth flow

### 5.3 Thời gian lưu trữ (Retention)

- Dữ liệu lưu trữ **cho đến khi** a:
  - Yêu cầu xóa (qua email, trong vòng 7 ngày)
  - Thu hồi quyền truy cập qua Meta (token vô hiệu ngay)
  - Gỡ cài đặt app khỏi thiết bị

- Sau khi a thu hồi quyền: token vô hiệu hóa, app không còn khả năng publish. Các file draft và asset local vẫn còn trên máy a cho đến khi a xóa thủ công.

## 6. Quyền của a

| Quyền | Cách thực hiện | Thời gian xử lý |
|-------|----------------|-----------------|
| 🔓 **Thu hồi quyền truy cập** | Meta Settings → Business Integrations → gỡ bỏ app "Quản Trị Page" | Ngay lập tức |
| 🗑️ **Yêu cầu xóa dữ liệu** | Email: `lamdo9@icloud.com` (tiêu đề: "Xóa dữ liệu") | Trong vòng **7 ngày** |
| 📥 **Yêu cầu xuất dữ liệu** | Email: `lamdo9@icloud.com` (tiêu đề: "Xuất dữ liệu") | Trong vòng **7 ngày** |
| 👁️ **Xem dữ liệu đang lưu** | Email: `lamdo9@icloud.com` (tiêu đề: "Xem dữ liệu") | Trong vòng **7 ngày** |
| ✏️ **Sửa thông tin** | Tự chỉnh sửa trong app hoặc file local | Ngay lập tức |
| ⚖️ **Khiếu nại** | Liên hệ email + data protection authority tại nước a | Theo luật địa phương |

## 7. Cookie và tracking

App **KHÔNG sử dụng cookie** hay bất kỳ công nghệ tracking nào:

- ❌ Không Google Analytics, GTM
- ❌ Không Facebook Pixel
- ❌ Không hotjar, mixpanel, segment
- ❌ Không third-party SDK
- ❌ Không browser fingerprinting
- ❌ Không cross-site tracking

App là **privacy-by-default** — không có tracking ẩn.

## 8. Quyền riêng tư trẻ em

App không hướng đến người dùng dưới 13 tuổi. Chúng tôi không cố ý thu thập dữ liệu từ trẻ em. Nếu a tin rằng trẻ em đã cung cấp dữ liệu, vui lòng liên hệ email để được xóa.

## 9. Thay đổi chính sách

Chính sách có thể được cập nhật để phản ánh:
- Thay đổi trong app
- Yêu cầu pháp lý mới (vd: GDPR updates)
- Yêu cầu từ Meta Platform Policy

- **Effective date**: 04/07/2026
- **Last updated**: 04/07/2026
- **Version**: 1.0

Thay đổi quan trọng sẽ:
1. Update ngày "Last updated" ở đầu trang
2. Thông báo qua email tới a (nếu đã gửi yêu cầu trước đó)
3. Tạo entry changelog ở cuối file

## 10. Liên hệ

Mọi câu hỏi, yêu cầu hoặc khiếu nại về chính sách bảo mật:

| Kênh | Chi tiết |
|------|----------|
| 📧 **Email** | `lamdo9@icloud.com` |
| 👤 **Owner** | Phúc Lâm |
| 📱 **App** | Quản Trị Page (App ID: 1477228617423402) |
| 📜 **Loại app** | Business |

**Thời gian phản hồi**: trong vòng 7 ngày làm việc.

---

## Phụ lục A — Permissions được sử dụng

App yêu cầu các Facebook Graph API permissions sau:

| Permission | Level | Mục đích | Lưu trữ data? |
|-----------|-------|----------|----------------|
| `pages_show_list` | Standard | Liệt kê pages a quản trị | Không |
| `pages_manage_posts` | Standard | Publish + schedule posts | ✅ Token + post ID |
| `pages_read_engagement` | Standard | Đọc metrics (reach, likes, comments) | ✅ Trong posted-log |
| `business_management` | Standard (optional) | Quản lý qua Business Manager | Không |

## Phụ lục B — Tham khảo chuẩn

- Meta Platform Policy: https://developers.facebook.com/policy/
- Meta App Review Guidelines: https://developers.facebook.com/app-review/
- GDPR Article 13 (Information to be provided): https://gdpr-info.eu/art-13-gdpr/

---

📜 **Bản nháp này tuân theo Meta Platform Policy và GDPR yêu cầu tối thiểu** về privacy disclosure cho app sử dụng `pages_manage_posts`, `pages_read_engagement`.
