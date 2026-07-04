# DEPLOY-CHECKLIST — Meta App Review Submission

Checklist từng bước để submit app **"Quản Trị Page"** vào Meta App Review.

---

## Phase 1: Hoàn thiện Privacy Policy (15-30 phút)

- [ ] **1.1** Mở `privacy-policy.vi.md` → review từng section một
- [ ] **1.2** Verify email `lamubboy@gmail.com` đúng (mục 10)
- [ ] **1.3** Verify các phần "❌ KHÔNG" (chỗ có thể thay đổi)
- [ ] **1.4** Mở `privacy-policy.en.md` → check đã dịch đúng nghĩa phần tiếng Việt
- [ ] **1.5** Tìm placeholder bất kỳ (`{{...}}`) → replace hết
- [ ] **1.6** Update `last_updated` + `effective_date` nếu có chỉnh sửa

## Phase 2: Deploy lên hosting công cộng (15 phút nếu GitHub)

### Option A — GitHub Pages (recommended)

```bash
# 1. Tạo repo mới tên "quatrit-page-privacy" trên github.com (public)
# 2. Local:
mkdir quatrit-page-privacy && cd quatrit-page-privacy

# 3. Tạo file index.html (convert từ .md sang HTML)
# Dùng pandoc: pandoc -s privacy-policy.en.md -o index.html
# Hoặc Markdown viewer tự động từ Obsidian/GitHub README

# 4. Copy 2 file vào repo:
cp /workspace/content/privacy/privacy-policy.en.md ./README.md
cp /workspace/content/privacy/privacy-policy.vi.md ./privacy.vi.md

# 5. Push & enable Pages
git init
git add .
git commit -m "Initial privacy policy"
git branch -M main
git remote add origin git@github.com:USERNAME/quatrit-page-privacy.git
git push -u origin main

# 6. Trên github.com → Settings → Pages → Source: main branch
# URL sẽ là: https://USERNAME.github.io/quatrit-page-privacy/
```

- [ ] **2.1** Repo public, có file `.md` ở root
- [ ] **2.2** Enable GitHub Pages (Settings → Pages → main branch)
- [ ] **2.3** Verify URL accessible (mở incognito)
- [ ] **2.4** URL output: `https://[username].github.io/quatrit-page-privacy/`

### Option B — Notion (nhanh hơn)

- [ ] **2B.1** Tạo Notion page mới (public access)
- [ ] **2B.2** Copy nội dung từ `privacy-policy.en.md` vào
- [ ] **2B.3** Click "Share" → "Publish to web" → bật
- [ ] **2B.4** Copy URL output

### Option C — Google Sites

- [ ] **2C.1** Tạo Google Sites mới
- [ ] **2C.2** Paste content từ `privacy-policy.en.md` vào editor
- [ ] **2C.3** Publish (đặt tên site dạng `quatrit-page`)
- [ ] **2C.4** URL output: `sites.google.com/view/quatrit-page/...`

## Phase 3: Switch Development → Live (5 phút)

Vào https://developers.facebook.com/apps/1477228617423402/

- [ ] **3.1** Sidebar → **Cài đặt ứng dụng** → **Thông tin cơ bản**
- [ ] **3.2** Fill **Privacy Policy URL** = URL output từ Phase 2 (file `privacy-policy.en.md` đã deploy)
- [ ] **3.3** Fill **Terms of Service URL** = URL output cho `terms-of-service.en.md` (hoặc cùng page)
- [ ] **3.4** Upload App icon (logo JPG/PNG ≤ 5MB)
- [ ] **3.5** Chọn Category (vd: "Business")
- [ ] **3.6** Verify email contact
- [ ] **3.7** Toggle **"Chế độ Phát triển"** → **"Chính thức"**
- [ ] **3.8** Save & confirm

## Phase 4: Submit App Review (15 phút chuẩn bị)

Vào https://developers.facebook.com/apps/1477228617423402/app-review/

- [ ] **4.1** Sidebar → **Xét duyệt ứng dụng** → **Quyền và tính năng**
- [ ] **4.2** Yêu cầu Advanced Access cho permission: `pages_manage_posts` (Quyền đăng bài)
- [ ] **4.3** Yêu cầu Advanced Access cho permission: `pages_read_engagement` (Quyền đọc lượt tương tác)
- [ ] **4.4** Điền form cung cấp thông tin chi tiết (Review Details) cho từng permission:

| Field | Nội dung gợi ý (Tiếng Anh bắt buộc) |
|-------|----------------|
| **Use case description** | "This is an internal command-line (CLI) tool used exclusively by the app administrator/owner (Phúc Lâm) to manage content scheduling and performance tracking for our own business Facebook pages. The tool runs on local servers/devices and utilizes long-lived Page Access Tokens. It does not have a public login interface or third-party users." |
| **Screenshots** | Chụp ảnh terminal khi gõ lệnh và file `.env` config (đã che token) + Ảnh trang Facebook Page hiển thị bài viết đã đăng. |
| **Test credentials** | Để trống hoặc tích chọn "No login required" (Vì đây là Server-to-server internal tool, reviewer không cần đăng nhập). |
| **Video demo** | **BẮT BUỘC 100%** (Meta ghi optional nhưng nếu thiếu CLI tool sẽ bị loại ngay). Xem file hướng dẫn chi tiết tại [`VIDEO-GUIDE.md`](./VIDEO-GUIDE.md). |

- [ ] **4.5** Nhấn **Submit** và chờ email xác nhận từ Meta.

## Phase 5: Đợi review (3-5 ngày làm việc)

- [ ] **5.1** Check email regularly (Meta gửi feedback + status)
- [ ] **5.2** Nếu REJECT → đọc lý do, fix, resubmit
- [ ] **5.3** Nếu APPROVED → test lại via API để confirm posts hiển thị cho user thường

---

## Verification sau khi APPROVED

```bash
# Quick test: xem page trên browser incognito (không login)
# → bài post qua API hiện ra public chưa?

# Verify via Graph API (của a):
curl -s -G https://graph.facebook.com/v20.0/<POST_ID> \
  --data-urlencode "access_token=<PAGE_TOKEN>" \
  --data-urlencode "fields=is_published,is_hidden"
# → is_published=true, is_hidden=false
```

## Files trong folder này

```
content/privacy/
├── README.md                    ← entry point
├── privacy-policy.vi.md         ← Tiếng Việt (review nội bộ)
├── privacy-policy.en.md         ← Tiếng Anh (submit cho Meta)
└── DEPLOY-CHECKLIST.md          ← file này
```

## Common pitfalls khi Meta reject

| ❌ Lỗi | ✅ Fix |
|--------|--------|
| Privacy Policy URL trả về 404 | Verify GitHub Pages enable đúng branch |
| Privacy Policy chỉ là placeholder | Phải có nội dung thật, ≥ 5 sections |
| Use case không rõ ràng | Giải thích cụ thể app làm gì + tại sao cần permission |
| Không có screenshot | Upload 5-10 ảnh UI flow |
| Token lộ ở client | Verify token chỉ lưu ở backend (local file OK) |

---

🎯 **Owner**: Phúc Lâm
🗓️ **Created**: 2026-07-04
📌 **Status**: Ready to deploy

