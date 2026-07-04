# Morzine Chalet Services & Concierge — deploy & edit guide

A bilingual (EN/FR) photo-led site with a working enquiry form powered by **Netlify Forms**. No build tools, no dependencies.

Files:
- `index.html` — the entire website (edit this)
- `netlify.toml` — Netlify config (publish dir + security headers)
- `assets/img/` — the chalet photos used across the page

---

## 1. Before you go live

Contact details are already filled in (email eoin.jfcc@gmail.com, phone +33 7 71 76 03 69, SIREN 897 699 773). To change any later, open `index.html` and search (Ctrl/Cmd-F) for **`CONFIG`** — the email and phone appear in the contact section and footer.

To swap or add photos: drop a JPG into `assets/img/` and update the matching `src="assets/img/…"` (or the `background-image` URL) in `index.html`. The pinned/background images are `IMG_2066.jpg` (hero), `IMG_2659.jpg` (sunset band), `IMG_3250.jpg` (winter band) and `IMG_1548.jpg` (wine section).

---

## 2. Deploy to Netlify (easiest → drag & drop)

1. Go to https://app.netlify.com/drop
2. Drag the **whole folder** (containing `index.html` and `netlify.toml`) onto the page.
3. Netlify gives you a live URL instantly (e.g. `jeffbuild.netlify.app`). Done.

### Deploy via Git (recommended for ongoing edits)
1. Put these files in a GitHub repo.
2. In Netlify: **Add new site → Import from Git → pick the repo.**
3. Build command: *(leave blank)*. Publish directory: `.`
4. Every push auto-deploys.

---

## 3. Turn on the quote form (Netlify Forms)

The form is already wired: `name="quote"`, `data-netlify="true"`, a honeypot, and a success message on redirect. Netlify auto-detects it on deploy — **no code changes needed.**

To receive submissions by email:
1. Netlify dashboard → your site → **Forms** → you'll see the `quote` form after the first deploy.
2. **Forms → Settings & notifications → Add notification → Email notification** → enter your email.
3. (Optional) Add Slack/webhook notifications the same way.

Test it: submit the form on the live site, then check **Forms → quote** for the entry.

> Note: Netlify Forms only work on the **deployed Netlify site**, not when opening `index.html` locally. Locally the form UI works but submissions won't be captured.

---

## 4. Custom domain (e.g. jeffbuild.fr)

1. Buy the domain (OVH, Gandi, Netlify, etc.).
2. Netlify → **Domain management → Add custom domain** → follow the DNS steps.
3. HTTPS is automatic (free Let's Encrypt certificate).

---

## 5. Good next steps
- Add a Google Business Profile for "JEFFBUILD, Le Biot" to show up in local search.
- Add real project photos + a couple of client testimonials to the site.
- Consider a `mentions légales` / privacy page (required for a French SAS site).
