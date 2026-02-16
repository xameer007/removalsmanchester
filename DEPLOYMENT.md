# Manchester Removals Website - Deployment Guide

## 🚀 Quick Deploy to Vercel

### Option 1: Deploy via Vercel CLI (Recommended)

1. **Install Vercel CLI globally:**
```bash
npm install -g vercel
```

2. **Login to Vercel:**
```bash
vercel login
```

3. **Navigate to project directory:**
```bash
cd removals-manchester-site
```

4. **Deploy to Vercel:**
```bash
vercel
```

5. **For production deployment:**
```bash
vercel --prod
```

### Option 2: Deploy via GitHub + Vercel Dashboard

1. **Push to GitHub:**
```bash
git init
git add .
git commit -m "Initial commit - Manchester Removals website"
git remote add origin YOUR_GITHUB_REPO_URL
git push -u origin main
```

2. **Connect to Vercel:**
- Go to https://vercel.com/new
- Import your GitHub repository
- Vercel will auto-detect settings
- Click "Deploy"

### Option 3: Deploy via Vercel Dashboard (Direct Upload)

1. **Compress your site:**
```bash
zip -r removals-manchester.zip .
```

2. **Upload to Vercel:**
- Go to https://vercel.com/new
- Select "Upload" option
- Drag and drop the zip file
- Click "Deploy"

---

## 📋 Pre-Deployment Checklist

Before deploying, update these items:

### 1. Contact Information
Replace placeholder contact details in ALL HTML files:
- Phone: `0161 234 5678` → Your actual phone
- Email: `info@manchesterremovals.co.uk` → Your email
- Address: `123 Deansgate, Manchester M3 2BW` → Your address

**Files to update:**
- index.html
- contact.html
- quote.html
- services.html
- areas.html
- about.html

### 2. Google Analytics (Optional but Recommended)
Add this code to the `<head>` section of each HTML file:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### 3. Form Integration
The contact and quote forms need backend integration. Choose one:

**Option A: Formspree (Easiest)**
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

**Option B: EmailJS**
```html
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>
  emailjs.init("YOUR_PUBLIC_KEY");
</script>
```

**Option C: Netlify Forms (if using Netlify)**
```html
<form data-netlify="true" name="contact">
```

### 4. Custom Domain Setup

After deployment, connect your domain:

1. Go to Vercel Dashboard → Your Project → Settings → Domains
2. Add your domain: `www.manchesterremovals.co.uk`
3. Update DNS records at your domain registrar:
   - Type: A, Name: @, Value: 76.76.21.21
   - Type: CNAME, Name: www, Value: cname.vercel-dns.com

---

## 🗂️ Project Structure

```
removals-manchester-site/
├── index.html              # Homepage (Main landing)
├── about.html              # About us page
├── contact.html            # Contact page with form
├── quote.html              # Quote request page
├── services.html           # Services overview
├── areas.html              # Coverage areas
├── vercel.json             # Vercel configuration
├── package.json            # Project metadata
└── README.md               # Documentation
```

---

## 🎯 SEO Optimization Post-Deployment

### 1. Submit Sitemap to Google
Create `sitemap.xml`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://yourdomain.com/</loc>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://yourdomain.com/services.html</loc>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://yourdomain.com/about.html</loc>
    <priority>0.7</priority>
  </url>
  <!-- Add all pages -->
</urlset>
```

Submit to: https://search.google.com/search-console

### 2. Create robots.txt
```
User-agent: *
Allow: /
Sitemap: https://yourdomain.com/sitemap.xml
```

### 3. Local SEO - Google My Business
1. Create/claim Google Business Profile
2. Use exact business name
3. Add NAP (Name, Address, Phone) matching website
4. Upload photos
5. Get reviews

---

## 🔧 Customization Options

### Change Colors
Edit CSS variables in each HTML file:
```css
:root {
    --noir: #0A0A0A;        /* Main dark color */
    --gold: #D4A574;        /* Accent color */
    --cream: #F5F5F0;       /* Background */
    --pearl: #FAFAF8;       /* Light background */
}
```

### Add More Pages
Create new HTML files following the template structure:
1. Copy header/nav from existing page
2. Update content in the main section
3. Keep consistent styling
4. Update navigation links

---

## 📊 Performance Optimization

### After Deployment:

1. **Test Page Speed:**
   - Google PageSpeed Insights
   - GTmetrix
   - WebPageTest

2. **Image Optimization:**
   - Use WebP format
   - Compress images
   - Add lazy loading

3. **Enable Caching:**
   Vercel handles this automatically

---

## 🐛 Troubleshooting

### Issue: Forms not sending
- Check form action URL
- Verify email service credentials
- Check browser console for errors

### Issue: Pages not loading
- Check file names match links
- Verify all files uploaded
- Check browser console

### Issue: Styling broken
- Clear browser cache
- Check font loading
- Verify CSS syntax

---

## 📞 Support

For deployment issues:
1. Check Vercel documentation: https://vercel.com/docs
2. Vercel Discord: https://vercel.com/discord
3. Stack Overflow: Tag with 'vercel'

---

## ✅ Post-Deployment Tasks

- [ ] Test all forms
- [ ] Verify all links work
- [ ] Test on mobile devices
- [ ] Check loading speed
- [ ] Submit to Google Search Console
- [ ] Set up Google Analytics
- [ ] Create Google My Business listing
- [ ] Test contact forms
- [ ] Update social media links
- [ ] Set up email forwarding
- [ ] Create backup of site

---

**Estimated deployment time:** 15-30 minutes
**Difficulty:** Beginner-friendly

Good luck with your deployment! 🚀
