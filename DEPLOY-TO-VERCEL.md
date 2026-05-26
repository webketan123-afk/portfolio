# 🚀 Deploy Your Portfolio to Vercel (Free)

## Method 1 — Drag & Drop (Easiest, 2 minutes)

1. Go to **https://vercel.com** and sign up free (use GitHub login)
2. On your dashboard click **"Add New → Project"**
3. Scroll down and click **"Deploy without a Git repository"**
4. **Drag and drop your `index.html` file** into the upload area
5. Click **Deploy** — done! You get a free URL like `ketan-portfolio.vercel.app`

---

## Method 2 — GitHub + Vercel (Best for auto-updates)

### Step 1 — Put your files on GitHub
```bash
# On your computer, open terminal/cmd in the folder with index.html
git init
git add index.html
git commit -m "Initial portfolio"

# Go to github.com → New repository → name it "portfolio"
# Then:
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
git branch -M main
git push -u origin main
```

### Step 2 — Connect to Vercel
1. Go to **https://vercel.com** → **"Add New → Project"**
2. Click **"Import Git Repository"** → select your `portfolio` repo
3. Leave all settings as default → click **Deploy**
4. ✅ Your site is live! Every `git push` will auto-redeploy

---

## Get a Custom Domain (Free .vercel.app or your own)

- Free subdomain: `your-name.vercel.app` — assigned automatically
- Custom domain: In Vercel dashboard → Project → Settings → Domains → add `yourdomain.com`

---

## Personalize Your Portfolio

Open `index.html` and update these sections:

| What to change | Where to find it |
|----------------|-----------------|
| Your name | Search `Ketan` — replace with your full name |
| Your photo | Find `about-photo-placeholder` — replace with `<img src="photo.jpg">` |
| Your email | Find `web.ketan@spaculus.info` |
| GitHub link | Find `https://github.com/` — add your profile URL |
| LinkedIn link | Find `https://linkedin.com/` — add your profile URL |
| WhatsApp | Find `https://wa.me/` — add `https://wa.me/91XXXXXXXXXX` |
| Years of exp | Find `data-count="5"` — change the number |
| Projects done | Find `data-count="40"` — change the number |
| Project cards | Each `project-card` block — edit name, description, tags |
| Timeline | Find `timeline-item` blocks — update your real experience |

---

## Wire Up the Contact Form (Real Emails)

1. Go to **https://www.emailjs.com** — sign up free (200 emails/month free)
2. Create a service + email template
3. Add this before `</body>` in your HTML:
```html
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>emailjs.init("YOUR_PUBLIC_KEY");</script>
```
4. Replace the `handleSubmit` function with:
```javascript
function handleSubmit(e) {
  e.preventDefault();
  emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', e.target)
    .then(() => alert('Message sent!'))
    .catch(() => alert('Failed. Try again.'));
}
```

---

## Performance Tips

- Compress your photo: use **https://squoosh.app** (target < 200KB)
- Test speed: **https://pagespeed.web.dev**
- Check mobile: Open DevTools → Ctrl+Shift+M

---

Built with: Three.js · GSAP · Typed.js · Pure HTML/CSS/JS  
Hosted on: Vercel (free forever for static sites)
