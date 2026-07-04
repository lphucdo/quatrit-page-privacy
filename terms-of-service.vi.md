---
title: "Điều khoản dịch vụ — Quản Trị Page"
app_name: "Quản Trị Page"
app_id: "1477228617423402"
version: 1.0
effective_date: 2026-07-04
last_updated: 2026-07-04
language: vi
target_audience: "Review nội bộ trước khi deploy"
status: draft
---

# Điều khoản dịch vụ — Quản Trị Page

> 📌 **Trạng thái**: BẢN NHÁP — chưa đăng công khai.
> Trước khi deploy: review từng section một, điền thông tin liên hệ thật, và xem `DEPLOY-CHECKLIST.md` để biết checklist tổng thể.

**Tên trong tài liệu này**: Quản Trị Page (App ID: `1477228617423402`)
**Chủ sở hữu**: cá nhân **Phúc Lâm**

---

## 1. Chấp nhận điều khoản

Bằng việc sử dụng Quản Trị Page, a đồng ý với các điều khoản trong tài liệu này. Nếu a không đồng ý, vui lòng không sử dụng dịch vụ.

## 2. Mô tả dịch vụ

Quản Trị Page là công cụ cho phép admin (chủ sở hữu Facebook Pages):

- Lên lịch đăng bài viết trên các Facebook Pages mà admin quản trị
- Xem metrics (reach, engagement) sau khi đăng
- Quản lý nhiều Pages từ một giao diện duy nhất
- Làm việc với nội dung (text, ảnh, video) do admin cung cấp

**App này KHÔNG phải là:**

- Công cụ marketing tự động (auto-reply, auto-comment, auto-message)
- Công cụ scraping hoặc theo dõi đối thủ
- Dịch vụ spam hoặc bulk messaging
- Marketplace hoặc dịch vụ đăng tin tự động
- Công cụ gửi thông báo hàng loạt

## 3. Trách nhiệm của người dùng

Khi sử dụng dịch vụ, a cam kết:

| ✅ A ĐƯỢC phép | ❌ A KHÔNG ĐƯỢC phép |
|----------------|----------------------|
| Đăng nội dung a có quyền sở hữu hoặc được phép đăng | Đăng nội dung spam, lừa đảo, vi phạm bản quyền |
| Tuân thủ Facebook/Meta Community Standards và Page Policies | Đăng nội dung có hại, khiêu dâm, bạo lực, phân biệt đối xử |
| Quản lý Pages a sở hữu hoặc có quyền admin | Cố ý vượt quota API của Meta |
| Thu hồi quyền truy cập khi không còn sử dụng | Chia sẻ Page Access Token với bên thứ ba |
| Báo cáo lỗi hoặc sự cố cho admin | Reverse-engineer app để trục lợi bất chính |
| | Dùng dịch vụ cho mục đích vi phạm pháp luật Việt Nam hoặc bất kỳ quốc gia nào |

## 4. Quyền sở hữu trí tuệ

### 4.1 Quyền của Quản Trị Page

- **Code ứng dụng**, giao diện, thiết kế, tài liệu là tài sản của **Phúc Lâm**
- Không được sao chép, phân phối, sửa đổi, hoặc tạo phái sinh khi chưa có sự cho phép bằng văn bản
- **License**: app được cung cấp miễn phí cho mục đích cá nhân của admin

### 4.2 Quyền của a

- **Nội dung a đăng** (caption, ảnh, video, link) thuộc về a
- App chỉ lưu trữ và publish theo chỉ dẫn của a
- A có thể xóa, sửa, xuất nội dung bất kỳ lúc nào

### 4.3 Quyền của bên thứ ba

- **"Facebook", "Meta", "Instagram"** là thương hiệu của Meta Platforms, Inc.
- App không claim ownership của trademarks này
- Mọi operation thông qua Meta API tuân theo [Meta Platform Policy](https://developers.facebook.com/policy/)

## 5. Dịch vụ bên thứ ba

Dịch vụ phụ thuộc vào:

- **Meta Graph API** — để publish + schedule + đọc metrics. Điều khoản Meta: https://www.facebook.com/terms
- **Mạng internet (HTTPS)** — để giao tiếp với Meta API

A đồng ý rằng:

- Availability của dịch vụ **phụ thuộc vào Meta** — mình không kiểm soát uptime của Meta
- Meta có thể **thay đổi API hoặc policy** bất kỳ lúc nào, có thể làm app tạm ngừng hoặc thay đổi chức năng
- Mình không chịu trách nhiệm về thay đổi từ phía Meta
- A tuân thủ [Meta Platform Policy](https://developers.facebook.com/policy/) khi sử dụng app

## 6. Khả dụng dịch vụ

Dịch vụ được cung cấp **"nguyên trạng" (as-is)** — mình **không bảo đảm** rằng:

- Dịch vụ luôn chạy liên tục 100% uptime
- Posts sẽ đăng đúng giờ trong mọi tình huống (phụ thuộc Meta API + mạng)
- Reach/engagement chính xác tuyệt đối (do thuật toán Meta quyết định)
- Không có lỗi hoặc sự cố

A chấp nhận rằng có thể xảy ra:

- **Maintenance/scheduled downtime** để cập nhật hoặc sửa lỗi
- **API rate-limit** từ phía Meta (đặc biệt khi đăng nhiều posts trong thời gian ngắn)
- **Tạm ngừng chức năng** khi Meta update Graph API version

## 7. Giới hạn trách nhiệm

Trong phạm vi pháp luật cho phép:

### ❌ Mình KHÔNG chịu trách nhiệm cho:

- Thiệt hại gián tiếp, ngẫu nhiên, đặc biệt, hoặc do hậu quả (bao gồm mất dữ liệu, mất lợi nhuận, mất uy tín)
- Posts bị Meta reject, flag là spam, hoặc xóa
- Thay đổi Meta API hoặc policy làm ảnh hưởng chức năng
- Hành vi của bên thứ ba (Meta, hosting, ISP)
- Lỗi hoặc downtime không do lỗi của mình

### ✅ Tổng trách nhiệm của mình:

- **Không vượt quá** số tiền a đã trả (nếu có) trong 12 tháng gần nhất
- App hiện được cung cấp **miễn phí** → giới hạn trách nhiệm thực tế = **0 VNĐ**

## 8. Chấm dứt

### 8.1 Quyền chấm dứt của mình

Mình có thể ngừng cung cấp dịch vụ hoặc thu hồi quyền truy cập của a nếu:

- A vi phạm điều khoản này
- Meta yêu cầu gỡ app hoặc thu hồi permissions
- Bất kỳ lý do hợp lý nào khác (sẽ thông báo trước nếu có thể)

### 8.2 Quyền chấm dứt của a

A có thể:

- Ngừng sử dụng dịch vụ bất kỳ lúc nào
- Thu hồi quyền truy cập app qua **Meta Settings → Business Integrations → gỡ app**
- Yêu cầu xóa dữ liệu qua email

### 8.3 Hiệu lực sau chấm dứt

- Điều khoản về **trách nhiệm** và **quyền sở hữu** vẫn có hiệu lực
- Dữ liệu của a sẽ được xóa trong vòng **7 ngày** (theo Privacy Policy)

## 9. Luật áp dụng và giải quyết tranh chấp

- Điều khoản này được điều chỉnh bởi **pháp luật Việt Nam**
- Mọi tranh chấp phát sinh sẽ được giải quyết **ưu tiên bằng thương lượng** giữa hai bên
- Nếu không thương lượng được, tranh chấp sẽ được đưa ra Tòa án có thẩm quyền tại Việt Nam
- Nếu bất kỳ điều khoản nào bị xem là **vô hiệu** hoặc **không thể thi hành**, các điều khoản còn lại vẫn có hiệu lực đầy đủ

## 10. Thay đổi điều khoản

- **Effective date**: 04/07/2026
- **Last updated**: 04/07/2026
- **Version**: 1.0

Mình có thể cập nhật điều khoản để phản ánh:

- Thay đổi dịch vụ
- Yêu cầu pháp lý mới
- Meta Policy updates
- Phản hồi từ người dùng

Thay đổi quan trọng sẽ:

1. Update ngày "Last updated" ở đầu file
2. Thông báo qua email tới a (nếu đã liên hệ trước đó)
3. Append changelog entry ở cuối file

Việc tiếp tục sử dụng dịch vụ sau khi điều khoản thay đổi = đồng ý với phiên bản mới.

## 11. Liên hệ

Mọi câu hỏi hoặc yêu cầu về điều khoản dịch vụ:

| Kênh | Chi tiết |
|------|----------|
| 📧 **Email** | `lamdo9@icloud.com` |
| 👤 **Owner** | Phúc Lâm |
| 📱 **App** | Quản Trị Page (App ID: 1477228617423402) |

**Thời gian phản hồi**: trong vòng **7 ngày làm việc**.

---

## Phụ lục A — Tóm tắt điều khoản quan trọng

| Điều khoản | Nội dung chính |
|-----------|----------------|
| **Loại dịch vụ** | Công cụ quản lý nội dung cho Facebook Pages (miễn phí) |
| **Không bảo hành** | "As-is" — không đảm bảo uptime, accuracy |
| **Không spam** | Cấm bulk messaging, auto-reply, scraping |
| **Tuân thủ Meta** | Mọi hoạt động qua Meta API phải theo Meta Policy |
| **Dữ liệu của a** | A sở hữu; có thể xóa/xuất bất kỳ lúc nào |
| **Luật áp dụng** | Việt Nam |
| **Liên hệ** | lamdo9@icloud.com |

---

## Phụ lục B — Tham khảo

- [Meta Platform Policy](https://developers.facebook.com/policy/)
- [Meta Terms of Service](https://www.facebook.com/terms)
- [Facebook Community Standards](https://transparency.fb.com/policies/community-standards/)
- [Luật An toàn thông tin mạng Việt Nam 2015](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Luat-an-toan-thong-tin-mang-2015-98-2015-QH13.aspx)
- [Nghị định 64/2007/NĐ-CP về ứng dụng CNTT trong quản lý nhà nước](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Nghi-dinh-64-2007-ND-CP-ung-dung-cong-nghe-thong-tin-trong-hoat-dong-co-quan-nha-nuoc-5959.aspx)

---

📜 **Bản nháp này tuân theo Meta Platform Policy** và pháp luật Việt Nam về dịch vụ điện tử.
