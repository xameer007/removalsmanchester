# 🚀 QUICK START GUIDE

## Deploy in 5 Minutes

### Step 1: Install Vercel CLI
```bash
npm install -g vercel
```

### Step 2: Login
```bash
vercel login
```

### Step 3: Deploy
```bash
cd removals-manchester-site
vercel --prod
```

**Done!** Your site is live.

---

## Before You Deploy - 3 Critical Updates

### 1. Update Phone Numbers
Find and replace in ALL files:
- `0161 234 5678` → Your phone
- `07700 900 123` → Your emergency phone

### 2. Update Email
Find and replace in ALL files:
- `info@manchesterremovals.co.uk` → Your email

### 3. Update Address
Find and replace in ALL files:
- `123 Deansgate, Manchester M3 2BW` → Your address

---

## Form Integration (Choose One)

### Option A: Formspree (Easiest - 5 min)
1. Sign up at https://formspree.io
2. Get your form endpoint
3. In `contact.html` and `quote.html`, update:
   ```html
   <form action="https://formspree.io/f/YOUR_ID" method="POST">
   ```

### Option B: Keep JavaScript Handler
Forms currently show alert messages. To send emails:
1. Sign up for EmailJS
2. Add their script
3. Configure email template

---

## Custom Domain Setup

### After Vercel Deployment:
1. Go to Vercel Dashboard → Settings → Domains
2. Add: `www.yourcompany.co.uk`
3. Update DNS at your registrar:
   - A Record: @ → 76.76.21.21
   - CNAME: www → cname.vercel-dns.com

---

## File Structure

```
removals-manchester-site/
├── index.html          ← Homepage (main landing)
├── about.html          ← About us
├── contact.html        ← Contact page + form
├── quote.html          ← Quote request + form
├── services.html       ← All services
├── areas.html          ← Coverage areas
├── vercel.json         ← Vercel config
└── package.json        ← Project info
```

---

## Need Help?

- **Deployment issues?** → Check DEPLOYMENT.md
- **Customization?** → Check README.md
- **Overview?** → Check PROJECT-SUMMARY.md

---

**⏱️ Total time:** 5-10 minutes
**💰 Cost:** Free (Vercel free tier)
**🔧 Skill level:** Beginner

Let's go! 🚀
