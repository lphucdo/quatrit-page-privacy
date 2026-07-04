# Privacy / Legal Documents

Folder này chứa tài liệu pháp lý cho Meta App **"Quản Trị Page"** (App ID: 1477228617423402) — dùng để submit cho Meta for Developers App Review.

## Files

| File | Ngôn ngữ | Mục đích | Trạng thái |
|------|----------|----------|------------|
| [`index.html`](./index.html) | 🇻🇳/🇬🇧 Song ngữ | Trang chủ pháp lý hoàn thiện để deploy GitHub Pages | ✨ Ready |
| [`privacy-policy.vi.md`](./privacy-policy.vi.md) | 🇻🇳 Tiếng Việt | Bản nháp Privacy Policy (review nội bộ) | 📝 Draft |
| [`privacy-policy.en.md`](./privacy-policy.en.md) | 🇬🇧 English | Bản nháp Privacy Policy tiếng Anh | 📝 Draft |
| [`terms-of-service.vi.md`](./terms-of-service.vi.md) | 🇻🇳 Tiếng Việt | Bản nháp Terms of Service (review nội bộ) | 📝 Draft |
| [`terms-of-service.en.md`](./terms-of-service.en.md) | 🇬🇧 English | Bản nháp Terms of Service tiếng Anh | 📝 Draft |
| [`DEPLOY-CHECKLIST.md`](./DEPLOY-CHECKLIST.md) | 🇻🇳 Việt | Checklist các bước submit App Review (Internal Tool) | 🔄 Updated |
| [`VIDEO-GUIDE.md`](./VIDEO-GUIDE.md) | 🇻🇳/🇬🇧 Song ngữ | Hướng dẫn quay video demo nộp Meta Review | ✨ New |

## Tại sao cần folder này?

Khi chuyển App từ **Development mode → Live mode** trên Meta for Developers, Meta yêu cầu:

1. **Privacy Policy URL** (URL thật, accessible)
2. **Terms of Service URL** (khuyến nghị nhưng optional)
3. Sau đó mới có thể submit **App Review** cho permission `pages_manage_posts`

## Workflow tổng thể

```
Bản draft (file .md trong Obsidian)
        ↓
A review + chỉnh sửa nội dung
        ↓
Upload lên hosting công cộng (GitHub Pages / Notion / Google Sites)
        ↓
Copy URL vào Meta for Developers → App Settings → Basic Information
        ↓
Switch toggle: Phát triển → Chính thức
        ↓
Submit App Review cho `pages_manage_posts`
```

## Chuẩn bị trước khi deploy

Trước khi a upload public, cần thay các placeholder trong file:

| Placeholder | Thay bằng |
|-------------|-----------|
| `lamdo9@icloud.com` | Email liên hệ (đã có sẵn) |
| `2026-07-04` | Effective date chính thức (đã OK) |
| `Phúc Lâm` | Tên admin (đã OK) |

## Hosting options (free)

| Service | URL format | Setup time | Custom domain |
|---------|-----------|-----------|----------------|
| **GitHub Pages** | `username.github.io/repo` | 10 min | ✅ Free |
| **Notion** | `notion.site/...` | 5 min | ❌ |
| **Google Sites** | `sites.google.com/view/...` | 5 min | ❌ |
| **Cloudflare Pages** | `project.pages.dev` | 15 min | ✅ Free |

→ Recommend: **GitHub Pages** (chuyên nghiệp, free, custom domain support, ổn định lâu dài).

## Lưu ý quan trọng

- ⚠️ Meta yêu cầu Privacy Policy phải accessible mà không cần login
- ⚠️ Reviewer của Meta sẽ click vào URL → nội dung phải hiển thị ngay
- ⚠️ Sau khi deploy, **không thay đổi** trừ khi phiên bản policy đã cập nhật (vì Meta có cache URL)

---

📜 **Version**: 1.0 (draft) — chưa submit Meta
🗓️ **Last updated**: 2026-07-04
