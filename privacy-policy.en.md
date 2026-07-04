---
title: "Privacy Policy — Quản Trị Page"
app_name: "Quản Trị Page"
app_id: "1477228617423402"
version: 1.0
effective_date: 2026-07-04
last_updated: 2026-07-04
language: en
target_audience: "Meta for Developers App Review"
status: draft
---

# Privacy Policy — Quản Trị Page

> 📌 **Status**: DRAFT — not yet published.
> Before deploying:
> - Verify contact email (`lamubboy@gmail.com`) is monitored
> - Review each section
> - See `DEPLOY-CHECKLIST.md` for the pre-submission checklist
> - Vietnamese version available at `privacy-policy.vi.md`


---

## 1. Overview

**"Quản Trị Page"** (App ID: `1477228617423402`, Business type) is a content management tool for Facebook Pages, developed and operated by **Phúc Lâm** (individual).

This privacy policy explains:
- What data we collect when you use the app
- How that data is used and protected
- Your rights regarding your data

The app is designed around the principle of **data minimization** — collecting only what is strictly necessary to perform its core function (scheduling and publishing posts across Facebook Pages).

## 2. Data We Collect

### 2.1 When you log in with Facebook

| Data | Purpose | Required |
|------|---------|----------|
| **Page Access Tokens** | Allow the app to call Graph API on your behalf to publish/schedule posts | ✅ Yes |
| **List of Pages** (id, name, category) | Display pages you manage | ✅ Yes |
| **Facebook name + avatar** | Verify admin identity | ✅ Yes |

This data is transmitted from Meta to your device via the standard Meta OAuth flow, scoped only to permissions you explicitly approve. The app does not interfere with this process.

### 2.2 When you use the app

| Data | Description | Where stored |
|------|-------------|--------------|
| **Caption text** | The text you input | Local Markdown file + asset folder |
| **Images / Videos** | Media you upload for posting | Local file in `drafts/` folder |
| **Schedule metadata** | Time and status (draft/scheduled/posted) | YAML frontmatter in Markdown files |
| **Facebook post IDs (after publish)** | IDs returned by Meta | `posted-log.jsonl` |

### 2.3 Technical logs

- **API errors**: error responses from Meta API (status code + message) → local log file
- **Response time**: used for performance debugging
- **Local IP**: only used for self-rate-limiting, never sent elsewhere

### 2.4 ❌ What we do NOT collect

- Personal information (PII) of your Page followers
- Private messages on Facebook
- Comments or user-generated content from your posts
- Cookies, browser fingerprints, device IDs
- Precise location (GPS) data
- Detailed device information

## 3. How We Use Your Data

Your data is used exclusively for the following purposes:

| Purpose | Data needed | Activity |
|---------|-------------|----------|
| ✅ **Schedule and publish posts** | Token + caption + media + schedule | Call Graph API at scheduled times |
| ✅ **Manage multiple Pages** | Pages list + IDs | Display in app UI |
| ✅ **Analyze post performance** | Reach, engagement (from Meta API) | Show metrics to admin |
| ✅ **Technical support** | Error logs | Debug failed API calls |

### We do NOT use your data to:

- ❌ Train AI / machine learning models
- ❌ Sell, rent, or share with third parties
- ❌ Build behavioral profiles for advertising
- ❌ Generate **automatic** content without admin consent (anti-spam)

## 4. Sharing with Third Parties

Your data is shared only with **Meta Platforms (Facebook, Inc.)** — the Graph API provider — within the scope of permissions you have granted.

We do NOT share with any other third parties, including:

- ❌ Analytics services (Google Analytics, Mixpanel, Amplitude, Facebook Pixel, etc.)
- ❌ Public cloud storage (AWS, GCP, Azure — except for Meta API calls)
- ❌ Advertisers, ad networks, or data brokers
- ❌ Any other third-party service

The app is **not classified as "spyware / surveillance"** and does not track users outside the granted scope.

## 5. Data Retention and Security

### 5.1 Where your data is stored

| Data type | Storage | Security |
|-----------|---------|----------|
| Page Access Tokens | Local `.env` file (encrypted at rest) | Restricted access (chmod 600) |
| Captions / images / videos | Local `drafts/` folder | No cloud sync |
| Posted-log | Local `.posted-log.jsonl` | No cloud sync |
| Technical logs | Local `/tmp/` files | Auto-delete after 24h |

**There is no cloud database.** Everything runs on the admin's personal device. There is no remote backend server.

### 5.2 Security measures

- ✅ HTTPS for all communication with Meta API
- ✅ Page Access Tokens never logged or committed to git
- ✅ Tokens revokable instantly via Meta Settings → Business Integrations
- ✅ App does not store passwords — uses only Meta OAuth flow

### 5.3 Retention period

- Data is retained **until** you:
  - Request deletion (via email, processed within 7 days)
  - Revoke access via Meta (token invalidated immediately)
  - Uninstall the app from your device

- After revocation: token is invalidated, app loses publish capability. Local draft and asset files remain on your device until you manually delete them.

## 6. Your Rights

| Right | How to exercise | Response time |
|------|----------------|---------------|
| 🔓 **Revoke access** | Meta Settings → Business Integrations → Remove "Quản Trị Page" app | Immediate |
| 🗑️ **Request data deletion** | Email `lamubboy@gmail.com` (subject: "Data Deletion") | Within **7 days** |
| 📥 **Request data export** | Email `lamubboy@gmail.com` (subject: "Data Export") | Within **7 days** |
| 👁️ **View stored data** | Email `lamubboy@gmail.com` (subject: "View Data") | Within **7 days** |
| ✏️ **Edit information** | Modify directly in app or local files | Immediate |
| ⚖️ **Complain** | Contact email + your local data protection authority | Per local law |

## 7. Cookies and Tracking

The app **does NOT use cookies or any tracking technology**:

- ❌ No Google Analytics, GTM
- ❌ No Facebook Pixel
- ❌ No Hotjar, Mixpanel, Segment
- ❌ No third-party SDKs
- ❌ No browser fingerprinting
- ❌ No cross-site tracking

The app is **privacy-by-default** — no hidden tracking.

## 8. Children's Privacy

The app is not directed at users under 13 years of age. We do not knowingly collect data from children. If you believe a child has provided data, please contact us via email for deletion.

## 9. Changes to This Policy

This policy may be updated to reflect:

- Changes to the app
- New legal requirements (e.g., GDPR updates)
- Requirements from Meta Platform Policy

- **Effective date**: July 4, 2026
- **Last updated**: July 4, 2026
- **Version**: 1.0

Material changes will:

1. Update the "Last updated" date at the top of this page
2. Notify via email (if you have previously contacted us)
3. Append a changelog entry at the bottom of this file

## 10. Contact

For any questions, requests, or complaints regarding this privacy policy:

| Channel | Details |
|---------|---------|
| 📧 **Email** | `lamubboy@gmail.com` |
| 👤 **Owner** | Phúc Lâm |
| 📱 **App** | Quản Trị Page (App ID: 1477228617423402) |
| 📜 **App type** | Business |

**Response time**: within 7 business days.

---

## Appendix A — Permissions Used

The app requests the following Facebook Graph API permissions:

| Permission | Level | Purpose | Data stored? |
|-----------|-------|---------|---------------|
| `pages_show_list` | Standard | List pages you manage | No |
| `pages_manage_posts` | Standard | Publish + schedule posts | ✅ Token + post ID |
| `pages_read_engagement` | Standard | Read metrics (reach, likes, comments) | ✅ In posted-log |
| `business_management` | Standard (optional) | Manage via Business Manager | No |

## Appendix B — Reference Standards

- Meta Platform Policy: https://developers.facebook.com/policy/
- Meta App Review Guidelines: https://developers.facebook.com/app-review/
- GDPR Article 13 (Information to be provided): https://gdpr-info.eu/art-13-gdpr/

---

📜 **This draft complies with Meta Platform Policy and GDPR minimum requirements** for privacy disclosure on an app using `pages_manage_posts` and `pages_read_engagement` permissions.

