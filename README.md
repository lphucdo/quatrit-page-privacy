# Privacy / Legal Documents

This folder contains legal documents for the Meta App **"Quản Trị Page"** (App ID: 1477228617423402) — used for submitting to Meta for Developers App Review.

## Files

| File | Language | Purpose | Status |
|------|----------|---------|--------|
| [`index.html`](./index.html) | 🇻🇳/🇬🇧 Bilingual | Production-ready legal page for GitHub Pages deployment | ✨ Ready |
| [`privacy-policy.vi.md`](./privacy-policy.vi.md) | 🇻🇳 Vietnamese | Privacy Policy draft (internal review) | 📝 Draft |
| [`privacy-policy.en.md`](./privacy-policy.en.md) | 🇬🇧 English | English Privacy Policy draft | 📝 Draft |
| [`terms-of-service.vi.md`](./terms-of-service.vi.md) | 🇻🇳 Vietnamese | Terms of Service draft (internal review) | 📝 Draft |
| [`terms-of-service.en.md`](./terms-of-service.en.md) | 🇬🇧 English | English Terms of Service draft | 📝 Draft |
| [`DEPLOY-CHECKLIST.md`](./DEPLOY-CHECKLIST.md) | 🇻🇳 Vietnamese | App Review submission checklist (Internal Tool) | 🔄 Updated |
| [`VIDEO-GUIDE.md`](./VIDEO-GUIDE.md) | 🇻🇳/🇬🇧 Bilingual | Demo video recording guide for Meta Review | ✨ New |

## Why is this folder needed?

When switching an App from **Development mode → Live mode** on Meta for Developers, Meta requires:

1. **Privacy Policy URL** (a real, publicly accessible URL)
2. **Terms of Service URL** (recommended but optional)
3. After that, you can submit an **App Review** for the `pages_manage_posts` permission

## Overall Workflow

```
Draft documents (.md files)
        ↓
Review & edit content
        ↓
Upload to public hosting (GitHub Pages / Notion / Google Sites)
        ↓
Copy URL into Meta for Developers → App Settings → Basic Information
        ↓
Switch toggle: Development → Live
        ↓
Submit App Review for `pages_manage_posts`
```

## Before Deploying

Before uploading publicly, make sure the following placeholders are replaced:

| Placeholder | Replace with |
|-------------|--------------|
| `lamdo9@icloud.com` | Contact email (already set) |
| `2026-07-04` | Official effective date (already OK) |
| `Phúc Lâm` | Admin name (already OK) |

## Hosting Options (Free)

| Service | URL Format | Setup Time | Custom Domain |
|---------|-----------|-----------|----------------|
| **GitHub Pages** | `username.github.io/repo` | 10 min | ✅ Free |
| **Notion** | `notion.site/...` | 5 min | ❌ |
| **Google Sites** | `sites.google.com/view/...` | 5 min | ❌ |
| **Cloudflare Pages** | `project.pages.dev` | 15 min | ✅ Free |

→ Recommended: **GitHub Pages** (professional, free, custom domain support, long-term stable).

## Important Notes

- ⚠️ Meta requires the Privacy Policy to be accessible without login
- ⚠️ Meta's reviewers will click the URL — content must load immediately
- ⚠️ After deploying, **do not change the URL** unless the policy version has been updated (Meta caches the URL)

---

📜 **Version**: 1.0 (draft) — not yet submitted to Meta  
🗓️ **Last updated**: 2026-07-04
