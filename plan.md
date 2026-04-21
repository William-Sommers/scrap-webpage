# Project Plan — Phế Liệu Hưng Thịnh Phát Website

> 🔒 **LOCAL ONLY — do not commit.** Full build plan from pre-call through post-launch support.

---

## Overview

| Field | Value |
|---|---|
| **Client** | Chú Hùng — CÔNG TY THU MUA PHẾ LIỆU HƯNG THỊNH PHÁT |
| **Domain target** | phelieuhungthinhphat.com |
| **Price** | 8.000.000 VND trọn gói + ~350k–2.5tr/năm running (chú trả) |
| **Total timeline** | ~10–14 ngày from deposit to delivery |
| **Deliverables** | Custom site + admin panel + hosting/DNS + SEO basics + training |

---

## Phase 0 — Pre-call prep ✅ *(done)*

- [x] Research competitor sites (Miền Nam, Bảo Minh, Ngọc Hải)
- [x] Build 3 frontend versions (`index.html`, `index2.html`, `index3.html`)
- [x] Iterate based on chú's feedback (hero fixes, diamond composition, stat cards)
- [x] Push to GitHub for version control
- [x] Research VN market pricing
- [x] Write pricing strategy → `CALL_PLAN.md`

---

## Phase 1 — Client alignment call

**Goal:** Lock scope, lock price (8tr), secure 50% deposit.
**Reference:** `CALL_PLAN.md` for full script.
**Duration:** ~30 min call + follow-up Zalo summary.

### Deliverable
- Signed agreement (Zalo message is fine) confirming:
  - Price: 8.000.000 VND
  - Scope: design + admin + deploy + SEO basic + training
  - Deposit: 4tr (50%)
  - Timeline: 1 tuần triển khai + 1 tuần polish
  - Running costs: chú trả thẳng nhà cung cấp

### Gate to Phase 2
- 4tr deposit received via bank transfer
- **Do NOT start Phase 2 work without deposit.**

---

## Phase 2 — Asset collection (Day 1–2)

Ask chú for via Zalo:

- [ ] **Logo** — nếu có file gốc (PNG/SVG). Nếu không, cháu làm logo đơn giản từ tên.
- [ ] **Bảng giá phế liệu hiện tại** — giá từng loại cập nhật mới nhất
- [ ] **Hình ảnh thực tế** — bãi phế liệu, xe tải, nhân viên làm việc (ít nhất 8–10 hình)
- [ ] **Thông tin liên hệ chính thức** — confirm lại phone, email, address, giờ làm việc
- [ ] **Khu vực thu mua** — TPHCM quận nào, tỉnh nào bao phủ
- [ ] **Lời giới thiệu công ty** — 1 đoạn chú tự viết, hoặc cháu viết chú duyệt
- [ ] **Tài khoản ngân hàng** — để cháu làm nút "Chuyển khoản" nếu cần
- [ ] **Facebook/Zalo/TikTok links** — social media chú đang dùng

**Deliverable:** folder `/assets/` với tất cả file chú gửi.

**Blocker risk:** Chú có thể gửi thiếu hoặc chậm. Mitigation: gửi list rõ ràng, nhắc sau 2 ngày, có fallback (dùng Unsplash stock nếu chú không có hình thật).

---

## Phase 3 — Tech stack decisions (Day 2)

Lock choices BEFORE starting development.

### Frontend — already decided
- **Plain HTML/CSS/JS** (already built)
- Font Awesome + Google Fonts (Be Vietnam Pro + Oswald)
- No framework (fast, cheap to host, easy to deploy)

### Backend/CMS — 3 options, pick one

| Option | Pros | Cons | Cost |
|---|---|---|---|
| **A. Google Sheets + JS fetch** | Zero infra. Chú edits a sheet, site reads it live. Chú already knows Sheets. | Limited to structured data (prices). Can't handle blog/news easily. No auth. | Free |
| **B. Decap CMS (Git-based)** | Real admin UI. Free. Chú logs in via browser. Commits auto to GitHub. | Requires GitHub account setup for chú. Bit of a learning curve. | Free |
| **C. Custom mini-admin (Node.js + SQLite)** | Fully tailored UX. Simple Vietnamese UI. | More dev time. Needs VPS or serverless function host. | ~$5/month VPS or Netlify Functions free tier |

**Recommendation: Option A (Sheets) for prices + Option B (Decap) for news/pages**
- Prices change weekly → Google Sheets (easiest for chú)
- News/about/gallery change monthly → Decap CMS (more polish)

### Hosting — 3 options

| Option | Pros | Cons | Cost |
|---|---|---|---|
| **Cloudflare Pages** | Free forever. Global CDN (fast in VN). HTTPS automatic. Git deploy. | US-company — slightly less "VN-native" feel. | Free |
| **Netlify** | Similar to Cloudflare. Decap CMS integration native. | Free tier has bandwidth caps. | Free → $19/month if bandwidth exceeds |
| **VN cPanel hosting (AZDIGI / Inet / Hawkhost VN)** | Familiar for VN clients. Vietnamese support. | ~200k/tháng. More manual. | ~2.2tr/year |

**Recommendation: Cloudflare Pages**
- Free forever (chú saves 2.2tr/year vs VN hosting)
- Fast in VN (Cloudflare has VN edge nodes)
- Auto HTTPS, auto deploy from GitHub
- Only cost = domain (~350k/năm)

**→ This means you can quote chú ~350k/year total running cost, not 2.5tr. Adjust that talking point.**

### Domain
- Register `phelieuhungthinhphat.com` via **PA Vietnam**, **iNet.vn**, or **Namecheap**
- Check availability first — if taken, have backups: `phelieuhungthinhphat.vn`, `hungthinhphatscrap.com`

---

## Phase 4 — Frontend finalization (Day 3–5)

Using `index3.html` as base.

### Tasks
- [ ] Replace Unsplash stock photos with chú's real photos
- [ ] Replace placeholder testimonials with real ones (ask chú for 2–3 real customers to quote)
- [ ] Populate real price table from bảng giá chú gửi
- [ ] Finalize "About us" copy
- [ ] Add real Facebook/Zalo/TikTok links
- [ ] Update all phone numbers (currently all 0933.231.777 — confirm this is his only number)
- [ ] Add favicon (from logo)
- [ ] Optimize images — convert to WebP, compress, lazy-load
- [ ] Test all internal anchors + external links
- [ ] Cross-browser test: Chrome, Coc Coc (important in VN), Safari, Firefox
- [ ] Mobile test on real phone (375px width)

### Staged reveal schedule (per CALL_PLAN.md)

| Day | Send to chú | Frame as |
|---|---|---|
| Day 3 | Screenshot of hero only | "Bản đầu của phần hero, cháu đang làm tiếp phần dưới" |
| Day 5 | Full `index.html` (actually v1 we built) | "Bản 1 xong, chú xem feedback" |
| Day 7 | `index2.html` | "Bản 2 cháu làm theo ý chú feedback" |
| Day 9 | `index3.html` final | "Bản final, đã đưa lên mạng thật rồi chú" |

In reality all 3 exist — drip-feed to make effort visible.

---

## Phase 5 — Admin panel / CMS (Day 4–7, parallel to Phase 4)

### If Option A (Google Sheets) for prices

- [ ] Create Google Sheet: `Bảng Giá Phế Liệu — Hưng Thịnh Phát`
  - Columns: `Loại | Mô tả | Đơn vị | Giá | Ngày cập nhật | Hiện/Ẩn`
- [ ] Publish sheet as CSV (File → Share → Publish to web)
- [ ] Write JS fetch in frontend to load CSV on page load
- [ ] Fallback: if fetch fails, show cached JSON version
- [ ] Share sheet with chú's Gmail (edit access)
- [ ] Test: edit cell in sheet → reload site → price updates ✅

### If Option B (Decap CMS) for news + content

- [ ] Add `/admin/` folder to repo with `index.html` + `config.yml`
- [ ] Configure collections: `news/`, `pages/about/`, `pages/gallery/`
- [ ] Set up Netlify Identity OR GitHub OAuth for login
- [ ] Create chú's admin account with his email
- [ ] Test: login → create a news post → publish → appears on site ✅

### Admin training assets
- [ ] Record 5-min screen recording: "Cách cập nhật giá trên Google Sheet"
- [ ] Record 5-min screen recording: "Cách đăng tin mới trên Decap"
- [ ] Upload to YouTube unlisted, send links to chú

---

## Phase 6 — Domain + DNS (Day 6–8)

- [ ] Check availability of `phelieuhungthinhphat.com`
- [ ] Register with PA Vietnam (VN option) OR Namecheap (cheaper, ~$10/year)
- [ ] Chú pays directly to registrar — forward his login credentials
- [ ] Add DNS records:
  - `A` record → Cloudflare Pages IP (auto via Cloudflare if domain is on Cloudflare)
  - `CNAME www` → apex domain
  - `TXT` record for Google Search Console verification
  - `MX` record if chú wants email forwarding
- [ ] Wait for DNS propagation (1–24 hours)
- [ ] Verify HTTPS is active (Cloudflare auto-issues)

---

## Phase 7 — Deployment (Day 8–9)

### Cloudflare Pages setup
- [ ] Create Cloudflare account (or use existing)
- [ ] Connect GitHub repo
- [ ] Configure build: output directory = root, no build command (static HTML)
- [ ] Set custom domain `phelieuhungthinhphat.com`
- [ ] Enable "Always Use HTTPS"
- [ ] Enable Auto Minify (CSS, JS, HTML)
- [ ] Enable Brotli compression

### Live checks
- [ ] `https://phelieuhungthinhphat.com` loads ✅
- [ ] `https://www.phelieuhungthinhphat.com` redirects to apex ✅
- [ ] HTTP → HTTPS redirect works ✅
- [ ] Page loads <2 seconds on 4G ✅
- [ ] Lighthouse score >90 across all 4 metrics ✅

---

## Phase 8 — SEO setup (Day 9–10)

### Technical SEO
- [ ] Update all `<title>` and `<meta description>` tags with local keywords
- [ ] Add Open Graph tags (og:title, og:description, og:image)
- [ ] Add Twitter Card tags
- [ ] Add `<meta name="robots" content="index, follow">`
- [ ] Add canonical URLs
- [ ] Add schema.org **LocalBusiness** markup with:
  - Name, address, phone, opening hours
  - Service area (TPHCM + tỉnh lân cận)
  - Price range indicator
  - Aggregate rating
- [ ] Create `/sitemap.xml`
- [ ] Create `/robots.txt`
- [ ] Verify all images have `alt` attributes in Vietnamese

### Off-page SEO
- [ ] Create **Google Business Profile** for the scrap yard
  - Upload real photos
  - Set service area
  - Add business description (Vietnamese)
  - Verify via postcard or phone
- [ ] Submit sitemap to **Google Search Console**
- [ ] Submit to **Bing Webmaster Tools** (Coc Coc uses Bing data)
- [ ] Register on VN business directories: **Trang Vàng VN**, **Yellowpages.vn**
- [ ] Set up basic **Google Analytics 4** tracking (optional — chú might not care)

### Local keyword targets
- "thu mua phế liệu Bình Tân"
- "thu mua phế liệu TPHCM giá cao"
- "phế liệu Hưng Thịnh Phát"
- "thu mua sắt vụn Bình Tân"
- "thu mua đồng TPHCM"

---

## Phase 9 — Testing & QA (Day 10–11)

### Functional testing
- [ ] All phone links (`tel:`) open dialer on mobile
- [ ] Zalo link opens Zalo app
- [ ] Messenger link works
- [ ] Contact form submits (via Formspree or Web3Forms free tier → chú's email)
- [ ] Google Maps embed loads
- [ ] Price table loads from Sheets (if Option A chosen)
- [ ] Admin login works (if Option B)

### Device testing
- [ ] iPhone Safari (smallest iPhone viewport)
- [ ] Android Chrome
- [ ] Coc Coc desktop (huge in VN — must work perfectly)
- [ ] Chrome desktop
- [ ] Low-end Android on 3G (many scrap customers are construction workers)

### Performance
- [ ] PageSpeed Insights >85 mobile, >95 desktop
- [ ] Total page size <500KB
- [ ] First Contentful Paint <1.5s

### SEO validation
- [ ] Schema.org validates via Google Rich Results Test
- [ ] sitemap.xml is valid
- [ ] Meta tags preview correctly in Zalo/Facebook share

---

## Phase 10 — Training & handover (Day 11–12)

### 1:1 training call with chú (30–45 min screen share via Zoom/Google Meet)

**Agenda:**
1. Tour of the live site (5 min)
2. How to update prices in Google Sheet (10 min)
3. How to post news/update content in Decap (10 min)
4. How to check Google Business messages (5 min)
5. How to respond to contact form submissions (5 min)
6. Q&A (10 min)

### Written handover package (PDF)
- [ ] `Hướng dẫn sử dụng website.pdf` (Vietnamese)
  - All login credentials
  - Step-by-step with screenshots
  - Common problems + solutions
  - Cháu's contact for support
- [ ] Sent via Zalo + email

### Credentials package (encrypted zip)
- Domain registrar login
- Cloudflare account login
- Google Sheet link
- Decap CMS login
- Google Business Profile login
- Formspree/Web3Forms dashboard
- GitHub repo link

---

## Phase 11 — Final payment & close (Day 12–14)

- [ ] Send chú Zalo message: "Website chạy chính thức, chú test thử hết các chức năng. Ok thì chú chuyển nốt 4tr giúp cháu."
- [ ] Wait for final 4tr transfer
- [ ] Issue receipt (Zalo screenshot is fine for VN small business)
- [ ] Ask for testimonial (use in your portfolio): *"Chú có thể cho cháu 1–2 câu nhận xét để cháu làm portfolio được không ạ?"*
- [ ] Ask for referrals: *"Chú có ai trong ngành cần làm web không, giới thiệu giúp cháu nha"*

---

## Phase 12 — Post-launch support (30 days free)

Include in 8tr:
- 30 days bug fix support
- 2 free content updates (if chú asks you vs. doing it himself)
- SSL renewal check
- Domain renewal reminder

**After 30 days:** offer maintenance retainer (optional).

### Maintenance retainer options
| Gói | Giá | Gồm |
|---|---|---|
| **Basic** | 300k/tháng | Bug fix + SSL/domain check + 1 update/tháng |
| **Pro** | 800k/tháng | + cập nhật giá hàng tuần + 1 bài tin/tháng + SEO monitor |
| **VIP** | 2tr/tháng | + chạy ads FB cơ bản + báo cáo tháng + 4 bài tin/tháng |

---

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Chú không trả đúng hạn | Medium | High | Đòi 50% deposit trước, KHÔNG bắt đầu Phase 2 nếu chưa có |
| Chú đổi ý nhiều về design | High | Medium | Lock design in writing sau Phase 4 reveal. Extra revisions = phụ phí 500k/lần |
| Chú yêu cầu scope creep | High | High | Scope locked in CALL_PLAN. Extras = báo giá riêng. |
| Domain đã bị đăng ký | Low | Medium | Backup domains chuẩn bị sẵn |
| Chú quên credentials | Very high | Low | PDF handover + credentials zip + bản giấy |
| Chú gọi cháu sửa lặt vặt hoài | Very high | High | 30 ngày miễn phí rõ ràng, sau đó retainer OR 300k/lần |
| Chú chia sẻ login cho người khác | High | Medium | Thêm điều khoản "không chia sẻ" trong handover |
| Cháu bận việc khác lúc chú cần gấp | Medium | High | Set SLA rõ: "reply trong 24h, fix trong 72h" |

---

## Tech stack final summary

| Layer | Choice | Why |
|---|---|---|
| **Frontend** | Plain HTML/CSS/JS | Fast, free, already built |
| **Fonts** | Google Fonts (Be Vietnam Pro, Oswald) | VN-friendly, free |
| **Icons** | Font Awesome CDN | Free tier sufficient |
| **Prices DB** | Google Sheets + JS fetch | Chú-friendly, zero cost |
| **CMS** | Decap CMS (for news/pages) | Free, GitHub-based, simple UI |
| **Hosting** | Cloudflare Pages | Free, fast in VN, auto SSL |
| **Domain** | Namecheap or PA Vietnam | ~350k/year |
| **Contact form** | Formspree or Web3Forms | Free tier for <50 msgs/month |
| **Analytics** | Google Analytics 4 (optional) | Free |
| **SEO tools** | Google Search Console + Business Profile | Free |

**Total recurring cost for chú: ~350k/năm** (domain only).

---

## Quick reference — session checklist before each work day

- [ ] Pull latest from GitHub
- [ ] Check Zalo for messages from chú
- [ ] Check Formspree for new contact form submissions (post-launch)
- [ ] Check Google Search Console for errors (post-launch)
- [ ] Do today's planned phase work
- [ ] Commit + push
- [ ] Send chú Zalo update (during reveal phase)

---

## Numbers cheatsheet

- **Total price:** 8.000.000đ
- **Deposit:** 4.000.000đ (before Phase 2)
- **Final:** 4.000.000đ (after Phase 11)
- **Running cost/năm (chú):** ~350.000đ (domain only, if Cloudflare path)
- **Your true timeline (internal):** 10–14 days
- **Client-facing timeline:** "khoảng 2 tuần"
- **Post-launch free support:** 30 days
- **Retainer starting rate:** 300k/month
