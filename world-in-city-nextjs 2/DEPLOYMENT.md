# 🚀 Quick Deployment Guide

## Get Your Site Live in 5 Minutes

### Option 1: Cloudflare Pages (GitHub) - RECOMMENDED

1. **Install & Build**
   ```bash
   npm install
   npm run build
   ```

2. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/world-in-city.git
   git push -u origin main
   ```

3. **Deploy on Cloudflare**
   - Go to https://dash.cloudflare.com
   - Click **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
   - Select your repo
   - **Framework**: Next.js (Static HTML Export)
   - **Build command**: `npm run build`
   - **Build output**: `out`
   - Click **Save and Deploy**

4. **Done!** Your site is live at `https://your-project.pages.dev`

---

### Option 2: Direct Upload (No GitHub Needed)

1. **Install & Build**
   ```bash
   npm install
   npm run build
   ```

2. **Upload to Cloudflare**
   - Go to https://dash.cloudflare.com
   - Click **Workers & Pages** → **Create** → **Pages** → **Upload assets**
   - Drag the `out` folder
   - Click **Deploy**

3. **Done!** Your site is live instantly.

---

### Option 3: Using Wrangler CLI

1. **Install & Build**
   ```bash
   npm install
   npm run build
   npm install -g wrangler
   ```

2. **Deploy**
   ```bash
   wrangler login
   wrangler pages deploy out --project-name=world-in-city
   ```

3. **Done!** Site is live.

---

## Adding a Custom Domain

1. In Cloudflare Pages project → **Custom domains**
2. Enter your domain (e.g., `theworldinacity.com`)
3. Cloudflare auto-configures DNS if domain is on Cloudflare
4. SSL certificate is automatically provisioned

---

## Next Steps

- Replace placeholder images in `/public`
- Update contact email in components
- Connect email capture to real service (Mailchimp, ConvertKit, etc.)
- Add analytics (Cloudflare Web Analytics, Google Analytics, etc.)

---

## Need Help?

- Full README: See `README.md`
- Cloudflare Docs: https://developers.cloudflare.com/pages
- Next.js Docs: https://nextjs.org/docs
