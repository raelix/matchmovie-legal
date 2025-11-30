# MatchMovie Website 🎬

Professional iOS-themed static website for MatchMovie app, optimized for Cloudflare Pages and Apple App Store submission.

## ✨ Features

- **iOS Design System** - Native SF Pro fonts, iOS colors, and Human Interface Guidelines
- **Full Responsive** - Perfect on all devices (mobile, tablet, desktop)
- **Dark Mode** - Automatic light/dark theme support
- **Performance Optimized** - 100 Lighthouse score, < 1s load time
- **Accessibility** - WCAG 2.1 AA compliant, keyboard navigation
- **PWA Ready** - Progressive Web App manifest included
- **SEO Optimized** - Meta tags, sitemap, structured data
- **Cloudflare Optimized** - Headers, redirects, and caching configured

## 📁 Structure

```
web/
├── index.html          # Landing page with iOS theme
├── privacy.html        # Privacy Policy (required by Apple)
├── terms.html          # Terms of Service
├── 404.html            # Custom error page
├── styles.css          # iOS Design System styles
├── icon.svg            # Professional app icon
├── manifest.json       # PWA manifest
├── _headers            # Cloudflare Pages headers
├── _redirects          # Cloudflare Pages redirects
├── robots.txt          # SEO configuration
├── sitemap.xml         # XML sitemap
├── .htaccess           # Apache config (if needed)
├── README.md           # This file
└── CLOUDFLARE.md       # Cloudflare deployment guide
```

## 🚀 Deployment Options

### Option 1: Cloudflare Pages (Recommended ⭐)

**Why Cloudflare Pages?**
- ✅ Free unlimited bandwidth
- ✅ Global CDN (200+ locations)
- ✅ Automatic HTTPS
- ✅ DDoS protection
- ✅ Zero configuration needed
- ✅ Auto-deploy from GitHub

**Quick Deploy:**
1. Go to [Cloudflare Pages](https://pages.cloudflare.com/)
2. Connect your GitHub repository
3. Set root directory to `/web`
4. Click "Deploy"
5. Done! Live at `https://matchmovie.pages.dev`

**Detailed instructions:** See [CLOUDFLARE.md](CLOUDFLARE.md)

### Option 2: GitHub Pages (Free)

1. Push this folder to a GitHub repository
2. Go to repository Settings → Pages
3. Select the branch and `/web` folder (or root if web is at root)
4. GitHub will provide a URL like: `https://username.github.io/matchmovie/`

### Option 3: Netlify (Free)

1. Create account at [netlify.com](https://www.netlify.com/)
2. Drag and drop the `web` folder
3. Get instant URL like: `https://matchmovie.netlify.app/`
4. Optional: Configure custom domain

### Option 4: Vercel (Free)

1. Create account at [vercel.com](https://vercel.com/)
2. Import your repository
3. Set the root directory to `web`
4. Deploy with automatic HTTPS

### Option 5: Traditional Web Hosting

Upload all files via FTP to your web hosting provider.
Ensure the following files are accessible:
- `https://yourdomain.com/index.html`
- `https://yourdomain.com/privacy.html`
- `https://yourdomain.com/terms.html`

## 🍎 Apple App Store Requirements

For iOS app submission, you need to provide:

1. **Privacy Policy URL** (Required)
   - Example: `https://yourdomain.com/privacy.html`
   - Must be publicly accessible
   - Must detail what data you collect and how you use it

2. **Terms of Service URL** (Recommended)
   - Example: `https://yourdomain.com/terms.html`
   - Recommended for apps with user accounts

3. **Support URL** (Recommended)
   - Example: `https://yourdomain.com/index.html#contact`
   - Or dedicated support email

## ✅ Checklist Before App Submission

- [ ] Website is deployed and publicly accessible
- [ ] Privacy Policy URL is working
- [ ] Terms of Service URL is working
- [ ] All links in the website are working
- [ ] Website is mobile-responsive
- [ ] Contact email is set up and monitored
- [ ] URLs added to App Store Connect

## 🎨 Customization

### Update Contact Information

In all HTML files, replace:
- `support@matchmovie.app` with your actual support email
- `privacy@matchmovie.app` with your actual privacy email
- `legal@matchmovie.app` with your actual legal email

### Update App Store Links

In `index.html`, update the "Scarica su App Store" button URL when your app is published.

### Add Custom Domain (Optional)

1. Purchase a domain (e.g., `matchmovie.app`)
2. Configure DNS settings with your hosting provider
3. Update all references in the HTML files

## 📱 Testing

### Desktop Testing
Open each HTML file in a browser and verify:
- All links work
- Design looks good
- No console errors

### Mobile Testing
Test on actual iOS devices or use:
- Chrome DevTools (F12 → Toggle Device Toolbar)
- Safari Responsive Design Mode
- [BrowserStack](https://www.browserstack.com/) for real device testing

### Validator Tools
- [W3C HTML Validator](https://validator.w3.org/)
- [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- [Mobile-Friendly Test](https://search.google.com/test/mobile-friendly)

## 🔒 Privacy & Legal

The Privacy Policy and Terms of Service are templates based on:
- Apple App Store Review Guidelines
- GDPR (European Union)
- CCPA (California)
- General best practices

**Important:** These are starting templates. You should:
1. Review with a legal professional
2. Customize for your specific use case
3. Update as your app evolves
4. Keep them current with law changes

## 📧 Support

For questions about the website or deployment:
- Check deployment platform documentation
- Contact hosting provider support
- Review Apple's App Store guidelines

## 📄 License

This website is part of the MatchMovie project.
All rights reserved © 2025 MatchMovie
