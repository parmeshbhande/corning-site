# Corning IT Solution — Website

Static 8-page marketing site (Home, About, Services, Portfolio, Contact, Careers, Privacy Policy, Terms of Service) for **citsolution.in**, built for GitHub Pages — no build step, no framework, just HTML/CSS/JS.

## Structure

```
cit/
├── index.html          Home
├── about.html           Company story, timeline, team
├── services.html        Service catalog, engagement models + FAQ
├── portfolio.html       Case studies (filterable) + featured ERP case study
├── contact.html          Contact form, map, contact FAQ
├── careers.html          Hiring philosophy + how we hire
├── privacy.html          Privacy Policy
├── terms.html            Terms of Service
├── css/style.css
├── js/main.js            Nav, scroll reveal, FAQ accordion, portfolio filter, form submit
└── assets/logo.svg
```

## 1. Connect the contact form (required)

The contact form on `contact.html` posts to **Formspree** so submissions are emailed out without the destination address ever appearing in the site's code. Formspree's free plan covers this.

1. Go to [formspree.io](https://formspree.io) and create a free account.
2. Create a new form and set its notification email to `hr@citsolution.in`.
3. Formspree gives you a form ID / endpoint like `https://formspree.io/f/abcd1234`.
4. Open `contact.html`, find this line near the `<form>` tag:
   ```html
   <form id="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
   Replace `YOUR_FORM_ID` with your real form ID.
5. Deploy, then submit the form once — Formspree will ask you to confirm the destination email the first time. After that, every submission is delivered automatically.

Until step 4 is done, the form will show a "backend not configured" message instead of submitting — it won't silently fail.

> The displayed public email `contactus@citsolution.in` is only for the mailto link/visual contact info — it's independent of where the form actually delivers.

## 2. Deploy to GitHub Pages

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

Then in the GitHub repo: **Settings → Pages → Source → Deploy from branch → main / (root)**.

If using a custom domain (`citsolution.in`):
1. Add a file named `CNAME` at the project root containing exactly: `citsolution.in`
2. In your domain DNS, add the records GitHub Pages requests (Settings → Pages will show them) — typically an `A`/`ALIAS` record to GitHub's IPs plus a `CNAME` for `www`.
3. Wait for DNS propagation, then enable "Enforce HTTPS" in the Pages settings.

## 3. Content to review before launch

Everything is production-ready copy, but a few things are placeholders you should personalize:
- Team titles in `about.html` (currently role-only — add real names/photos if you want).
- Testimonials on `index.html` (currently representative sample quotes — swap in real client quotes as you collect them).
- Portfolio projects in `portfolio.html` (currently illustrative case studies — replace with real project names/screenshots as available).
- Office address is set to 91Springboard, Creaticity, Yerawada, Pune, Maharashtra 411006 across footers, the Contact page, and the embedded map — update if this changes. No phone number is published.
- `privacy.html` and `terms.html` are solid boilerplate — have them reviewed by a lawyer before relying on them, especially for India's DPDP Act compliance.
# corning-site
