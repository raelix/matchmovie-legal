# Cloudflare Pages Deployment Guide

Complete guide for deploying MatchMovie website to Cloudflare Pages.

## 🚀 Why Cloudflare Pages?

- ✅ **Free hosting** with unlimited bandwidth
- ✅ **Global CDN** - Ultra-fast loading worldwide
- ✅ **Automatic HTTPS** with SSL certificates
- ✅ **DDoS protection** and security features
- ✅ **GitHub integration** - Auto-deploy on push
- ✅ **Custom domains** support
- ✅ **Edge computing** capabilities
- ✅ **Zero configuration** needed

## 📋 Prerequisites

1. **GitHub Account** (to host the repository)
2. **Cloudflare Account** (free tier is sufficient)
   - Sign up at https://dash.cloudflare.com/sign-up

## 🔧 Deployment Steps

### Method 1: Direct Upload (Fastest)

1. **Go to Cloudflare Pages**
   - Visit: https://dash.cloudflare.com/
   - Click "Workers & Pages" in the sidebar
   - Click "Create application" → "Pages" → "Upload assets"

2. **Upload Website Files**
   - Navigate to your `web/` folder
   - Drag and drop all files
   - Project name: `matchmovie`
   - Click "Deploy site"

3. **Done!**
   - Your site will be live at: `https://matchmovie.pages.dev`
   - Deployment takes ~1 minute

### Method 2: GitHub Integration (Recommended)

1. **Push Code to GitHub**
   ```bash
   # Already done! Your code is on GitHub
   git remote -v  # Verify remote repository
   ```

2. **Connect to Cloudflare Pages**
   - Go to https://dash.cloudflare.com/
   - Click "Workers & Pages"
   - Click "Create application" → "Pages"
   - Click "Connect to Git"
   - Select your GitHub repository: `raelix/matchmovie`

3. **Configure Build Settings**
   ```
   Project name: matchmovie
   Production branch: main
   Build command: (leave empty - it's a static site)
   Build output directory: /web
   Root directory: /web
   ```

4. **Deploy**
   - Click "Save and Deploy"
   - Cloudflare will build and deploy your site
   - First deployment takes ~2 minutes
   - Future deployments are automatic on every git push!

5. **Your Site is Live!**
   - Default URL: `https://matchmovie.pages.dev`
   - Or custom domain: `https://matchmovie.app` (see below)

## 🌐 Custom Domain Setup

### If you own a domain (e.g., matchmovie.app):

1. **In Cloudflare Pages**:
   - Go to your project
   - Click "Custom domains"
   - Click "Set up a custom domain"
   - Enter your domain: `matchmovie.app`

2. **Configure DNS**:
   - Add a CNAME record:
     ```
     Type: CNAME
     Name: @ (or www)
     Target: matchmovie.pages.dev
     Proxy: Yes (orange cloud)
     ```

3. **Wait for DNS propagation** (5-30 minutes)

4. **Enable HTTPS**:
   - Cloudflare automatically provisions SSL certificates
   - Your site will be accessible via `https://matchmovie.app`

### If you don't have a domain:

Your site will be available at:
- `https://matchmovie.pages.dev`

This URL is perfect for:
- App Store submission (Privacy Policy & Terms)
- Testing and development
- Sharing with beta testers

## 📱 Apple App Store URLs

After deployment, use these URLs in App Store Connect:

1. **Privacy Policy URL**:
   ```
   https://matchmovie.pages.dev/privacy.html
   ```
   Or with custom domain:
   ```
   https://matchmovie.app/privacy.html
   ```

2. **Terms of Service URL**:
   ```
   https://matchmovie.pages.dev/terms.html
   ```

3. **Support URL**:
   ```
   https://matchmovie.pages.dev/
   ```

## 🔄 Continuous Deployment

With GitHub integration:

1. **Make changes** to your website files
2. **Commit and push**:
   ```bash
   git add .
   git commit -m "Update website"
   git push
   ```
3. **Automatic deployment** - Cloudflare detects the push and deploys automatically
4. **Live in ~1 minute** - Your changes are live!

## 🎨 Testing Before Deployment

### Local Testing

1. **Use Python's built-in server**:
   ```bash
   cd web/
   python3 -m http.server 8000
   ```
   Visit: http://localhost:8000

2. **Use Node.js http-server**:
   ```bash
   npx http-server web/ -p 8000
   ```
   Visit: http://localhost:8000

3. **Use PHP server**:
   ```bash
   cd web/
   php -S localhost:8000
   ```

### Preview Deployments

Cloudflare Pages creates preview deployments for every branch and PR:
- Each git branch gets its own URL
- Perfect for testing before merging to main
- Example: `https://branch-name.matchmovie.pages.dev`

## ⚡ Performance Optimization

Already configured in your website:

- ✅ **Cloudflare CDN** - Content served from 200+ locations worldwide
- ✅ **HTTP/2 & HTTP/3** - Modern protocols enabled
- ✅ **Brotli Compression** - Smaller file sizes
- ✅ **Caching headers** - Configured in `_headers` file
- ✅ **Image optimization** - SVG icons are lightweight
- ✅ **Minification** - CSS is optimized
- ✅ **Edge caching** - Static assets cached at the edge

### Performance Scores

Expected Lighthouse scores:
- Performance: 95-100
- Accessibility: 100
- Best Practices: 100
- SEO: 100

## 🔒 Security Features

Configured in `_headers` file:

- ✅ **HTTPS** - Automatic SSL certificates
- ✅ **Security headers** - XSS, clickjacking protection
- ✅ **CSP** - Content Security Policy
- ✅ **DDoS protection** - Cloudflare's network
- ✅ **Bot mitigation** - Automatic bot detection
- ✅ **Rate limiting** - Protection against abuse

## 🔧 Advanced Configuration

### Environment Variables

If needed in the future, set in Cloudflare Pages settings:
```
Settings → Environment variables
```

### Build Configuration

Cloudflare Pages supports:
- Static sites (current setup - zero config needed!)
- Build frameworks (Next.js, Gatsby, Hugo, etc.)
- Serverless functions (Pages Functions)

### Analytics

Enable Web Analytics:
1. Go to project settings
2. Click "Web Analytics"
3. Enable analytics
4. View real-time traffic and performance data

## 📊 Monitoring

### Check Deployment Status

```bash
# View recent deployments
https://dash.cloudflare.com/ → Your Project → Deployments
```

### Build Logs

- Available in the Cloudflare dashboard
- Shows deployment progress and any errors
- Useful for debugging

### Real-time Analytics

- Page views
- Bandwidth usage
- Geographic distribution
- Performance metrics

## 🐛 Troubleshooting

### Deployment Failed

1. Check build logs in Cloudflare dashboard
2. Verify all files are in `/web` directory
3. Ensure no build command is set (static site)

### 404 Errors

- Configured in `_redirects` file
- Custom 404 page: `404.html`
- Cloudflare will serve it automatically

### Domain Not Working

1. Check DNS propagation: https://dnschecker.org/
2. Verify CNAME record points to `matchmovie.pages.dev`
3. Ensure SSL/TLS mode is set to "Full" or "Flexible"
4. Wait up to 24 hours for full propagation

### CSS/Images Not Loading

1. Check browser console for errors
2. Verify file paths are relative (e.g., `./styles.css`)
3. Clear browser cache
4. Check `_headers` file for correct MIME types

## 📚 Resources

- **Cloudflare Pages Docs**: https://developers.cloudflare.com/pages/
- **Headers Configuration**: https://developers.cloudflare.com/pages/platform/headers/
- **Redirects**: https://developers.cloudflare.com/pages/platform/redirects/
- **Custom Domains**: https://developers.cloudflare.com/pages/platform/custom-domains/
- **Cloudflare Community**: https://community.cloudflare.com/

## ✅ Pre-Deployment Checklist

Before deploying, ensure:

- [ ] All HTML files have proper meta tags
- [ ] Icon files (icon.svg, manifest.json) are present
- [ ] Privacy Policy and Terms of Service are complete
- [ ] Contact emails are updated (support@matchmovie.app)
- [ ] All links work correctly
- [ ] Website tested locally
- [ ] Responsive design tested on mobile
- [ ] Dark mode tested
- [ ] Accessibility tested (keyboard navigation, screen readers)

## 🎉 Post-Deployment

After successful deployment:

1. **Test the live site**
   - Visit your Cloudflare Pages URL
   - Test all links and pages
   - Check on mobile devices
   - Test in different browsers

2. **Update App Store Connect**
   - Add Privacy Policy URL
   - Add Terms of Service URL
   - Add Support URL

3. **Monitor performance**
   - Check Cloudflare Analytics
   - Run Lighthouse audit
   - Monitor for any errors

4. **Optional: Set up monitoring**
   - Uptime monitoring (e.g., UptimeRobot)
   - Error tracking (e.g., Sentry)
   - Analytics (already included with Cloudflare)

---

## 🚀 Quick Start Summary

For the fastest deployment:

```bash
# 1. Visit Cloudflare Pages
https://dash.cloudflare.com/ → Workers & Pages → Create

# 2. Connect your GitHub repo
Select: raelix/matchmovie
Branch: main
Root directory: /web

# 3. Deploy!
Click "Save and Deploy"

# 4. Done! Your site is live at:
https://matchmovie.pages.dev
```

That's it! Your iOS-themed MatchMovie website is now hosted on Cloudflare's global CDN with enterprise-grade security and performance. 🎬
