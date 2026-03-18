# The World In A City

A premium, cinematic Next.js website for the 2026 FIFA World Cup documentary project.

![Next.js](https://img.shields.io/badge/Next.js-14.2.3-black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.4.5-blue)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4.4-38bdf8)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-11.2.10-ff0055)

## 🎯 Overview

This is a production-ready, fully static Next.js website built for deployment to **Cloudflare Pages**. The site features:

- ✅ **Static Export** - No server-side rendering required
- ✅ **Cinematic Design** - Premium, dark theme with smooth animations
- ✅ **Fully Responsive** - Mobile-first design
- ✅ **Optimized Performance** - Fast loading, smooth scrolling
- ✅ **SEO Ready** - Proper meta tags and semantic HTML

## 🚀 Quick Start

### Prerequisites

- **Node.js 18+** (recommended: 20.x LTS)
- **npm** or **yarn** or **pnpm**

### Installation

```bash
# Clone or extract the project
cd the-world-in-a-city

# Install dependencies
npm install
# or
yarn install
# or
pnpm install
```

### Development

```bash
# Start development server
npm run dev

# Open http://localhost:3000 in your browser
```

### Build

```bash
# Create production build (static export)
npm run build

# This creates an /out directory with static HTML/CSS/JS
```

### Preview Production Build Locally

```bash
# After building, you can preview the static site
npx serve out

# or using Python
cd out && python3 -m http.server 8000
```

## 📦 Project Structure

```
the-world-in-a-city/
├── src/
│   ├── app/
│   │   ├── layout.tsx          # Root layout with fonts
│   │   ├── page.tsx             # Main page
│   │   └── globals.css          # Global styles
│   └── components/
│       ├── Navigation.tsx       # Sticky nav
│       ├── Footer.tsx           # Footer
│       └── sections/
│           ├── Hero.tsx
│           ├── WhatThisIs.tsx
│           ├── WhyItMatters.tsx
│           ├── Cities.tsx
│           ├── Sponsors.tsx
│           ├── Credibility.tsx
│           ├── Platform.tsx
│           ├── Watch.tsx
│           ├── EmailCapture.tsx
│           ├── Technology.tsx
│           └── FinalCTA.tsx
├── public/                      # Static assets (add images here)
├── next.config.js              # Next.js config (static export)
├── tailwind.config.js          # Tailwind config with brand colors
├── tsconfig.json               # TypeScript config
├── package.json                # Dependencies
└── README.md                   # This file
```

## 🌐 Deploy to Cloudflare Pages

### Method 1: GitHub Integration (Recommended)

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/world-in-city.git
   git push -u origin main
   ```

2. **Connect to Cloudflare Pages**
   - Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Navigate to **Workers & Pages** → **Create Application** → **Pages**
   - Click **Connect to Git**
   - Select your repository
   
3. **Configure Build Settings**
   ```
   Framework preset: Next.js (Static HTML Export)
   Build command: npm run build
   Build output directory: out
   ```

4. **Deploy**
   - Click **Save and Deploy**
   - Your site will be live at: `https://your-project.pages.dev`

### Method 2: Direct Upload (Wrangler CLI)

1. **Install Wrangler**
   ```bash
   npm install -g wrangler
   ```

2. **Authenticate**
   ```bash
   wrangler login
   ```

3. **Build the site**
   ```bash
   npm run build
   ```

4. **Deploy**
   ```bash
   wrangler pages deploy out --project-name=world-in-city
   ```

### Method 3: Drag and Drop

1. **Build the site**
   ```bash
   npm run build
   ```

2. **Upload to Cloudflare**
   - Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Navigate to **Workers & Pages** → **Create Application** → **Pages**
   - Click **Upload assets**
   - Drag and drop the `out` folder
   - Click **Deploy**

## 🔧 Custom Domain Setup

1. **Add Custom Domain in Cloudflare Pages**
   - Go to your Pages project
   - Click **Custom domains**
   - Click **Set up a custom domain**
   - Enter your domain (e.g., `theworldinacity.com`)

2. **Configure DNS**
   - If domain is on Cloudflare:
     - DNS records are automatically added
   - If domain is elsewhere:
     - Add CNAME record: `your-project.pages.dev`

3. **SSL/TLS**
   - Cloudflare automatically provisions SSL certificate
   - Your site will be accessible via HTTPS

## 🎨 Customization

### Brand Colors (Tailwind Config)

```js
colors: {
  'ink': '#0B0B0B',        // Primary dark background
  'pitch': '#111111',      // Secondary dark
  'grass': '#0F2A25',      // Dark green
  'gold': '#C6A85B',       // Primary accent
  'chalk': '#EDEDED',      // Text color
  'warm-gray': '#8A8478', // Secondary text
}
```

### Adding Images

1. Place images in `/public` folder
2. Reference in components: `/your-image.jpg`

Example:
```tsx
<img src="/hero-background.jpg" alt="Hero" />
```

### Modifying Content

All content is in the component files under `/src/components/sections/`. Edit the text directly in each component.

## 🔍 Static Export Configuration

This project is configured for **static export** in `next.config.js`:

```js
const nextConfig = {
  output: 'export',           // Enable static export
  images: {
    unoptimized: true,        // Disable Next.js image optimization
  },
  trailingSlash: true,        // Add trailing slashes to URLs
}
```

### Important Notes:

- ✅ No API routes (not supported in static export)
- ✅ No server-side rendering (SSR)
- ✅ No dynamic routes with `getServerSideProps`
- ✅ All routing is client-side
- ✅ Perfect for Cloudflare Pages

## 🎭 Features

### Animations (Framer Motion)
- Smooth scroll-triggered animations
- Fade-in and slide-in effects
- Hover animations on cards
- Optimized for performance

### Responsive Design
- Mobile-first approach
- Breakpoints: 640px (sm), 768px (md), 1024px (lg), 1280px (xl)
- Touch-friendly interactions

### SEO Optimization
- Semantic HTML
- Meta tags in layout
- Proper heading hierarchy
- Alt text placeholders

## 📊 Performance

- **Lighthouse Score Target**: 95+ across all metrics
- **Build Output**: Static HTML/CSS/JS
- **Bundle Size**: Optimized with tree-shaking
- **Loading Speed**: Fast (served from Cloudflare edge)

## 🐛 Troubleshooting

### Build Errors

**Error: "Module not found"**
```bash
# Delete node_modules and reinstall
rm -rf node_modules
npm install
```

**Error: "Port 3000 already in use"**
```bash
# Kill process on port 3000
npx kill-port 3000
# or use a different port
npm run dev -- -p 3001
```

### Deployment Issues

**Error: "Build failed"**
- Check that `npm run build` works locally first
- Ensure Node.js version is 18+ on Cloudflare
- Check build logs for specific errors

**Images not loading**
- Ensure images are in `/public` directory
- Use absolute paths: `/image.jpg` not `./image.jpg`

## 📝 Environment Variables

This project doesn't require environment variables for basic functionality. If you add API integrations (e.g., email capture), add them to Cloudflare Pages:

1. Go to your Pages project
2. Click **Settings** → **Environment variables**
3. Add variables for **Production** and **Preview**

## 🔐 Security

- No sensitive data in code
- All dependencies regularly updated
- Static site = minimal attack surface
- HTTPS enforced by Cloudflare

## 📚 Tech Stack

- **Framework**: Next.js 14.2.3 (App Router)
- **Language**: TypeScript 5.4.5
- **Styling**: Tailwind CSS 3.4.4
- **Animations**: Framer Motion 11.2.10
- **Icons**: Lucide React
- **Fonts**: Inter, Montserrat (Google Fonts)
- **Hosting**: Cloudflare Pages

## 🤝 Support

For issues or questions:
1. Check this README
2. Review Next.js [static export docs](https://nextjs.org/docs/app/building-your-application/deploying/static-exports)
3. Check Cloudflare Pages [documentation](https://developers.cloudflare.com/pages)

## 📄 License

© 2025 The World In A City. All Rights Reserved.

---

**Built with ⚡ by Hilton Sports Group**
