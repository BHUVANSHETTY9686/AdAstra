# Ad Astra - Game Studio Website

A modern, cinematic landing page for Ad Astra game studio.

## 🚀 Live Site

**GitHub Pages:** https://bhuvanshetty9686.github.io/AdAstra/adastra.html  
*(Enable in Settings → Pages → Source: main branch)*

## 📁 Project Structure

```
AdAstra/
├── adastra.html          # Main website file
├── assets/
│   ├── images/          # Your images go here
│   └── videos/          # Your videos go here
└── README.md
```

## 🎨 How to Add Your Assets

### Option 1: Local Files (Recommended)

1. **Add your images to `assets/images/`:**
   - `hero-bg.jpg` - Main hero background
   - `project-nebula.jpg` - Featured game 1
   - `void-walker.jpg` - Featured game 2  
   - `starlight-chronicles.jpg` - Featured game 3
   - `gallery-1.jpg` through `gallery-6.jpg` - Gallery images

2. **Update image paths in adastra.html:**
   - Replace Unsplash URLs with `assets/images/your-file.jpg`

3. **Commit and push:**
   ```bash
   git add .
   git commit -m "Add assets"
   git push origin main
   ```

### Option 2: Use CDN Links (jsDelivr)

After pushing images to GitHub, use:
```
https://cdn.jsdelivr.net/gh/BHUVANSHETTY9686/AdAstra/assets/images/hero-bg.jpg
```

### Option 3: External Hosting

- **Cloudinary** - cloudinary.com (free tier)
- **Imgur** - imgur.com (quick uploads)
- **Google Drive** - Share as public link

## 🔗 What Links to Update

### Social Media Links (around line 320-350):
- Discord server invite
- Twitter/X profile
- YouTube channel
- Instagram profile
- LinkedIn company page
- TikTok account

### External Links (around line 200-240):
- Steam store page
- Oculus/Meta Quest store
- Xbox store page
- Press kit download (Google Drive/Dropbox)

### Contact Info (around line 337):
- Email address
- Location
- Booking/calendar link

### Showreel Video (around line 174):
Replace YouTube embed URL with your trailer

## 🛠️ Quick Commands

```bash
# View locally
start adastra.html

# After making changes
git add .
git commit -m "Update content"
git push origin main

# Your site updates automatically on GitHub Pages in ~1 min
```

## ✅ Next Steps

1. **Enable GitHub Pages:**
   - Go to repo Settings
   - Click "Pages" in sidebar
   - Source: Deploy from main branch
   - Save

2. **Add your images** to `assets/images/`

3. **Replace placeholder links** with real URLs

4. **Test locally** before pushing

## 🎮 Features

- ✅ Fully responsive design
- ✅ Mobile navigation menu
- ✅ Smooth scroll anchors
- ✅ Glass-morphism cards
- ✅ Hover animations
- ✅ No backend/database needed
- ✅ Fast loading (Tailwind CDN)
- ✅ SEO-ready

---

**Built with love among the stars** ⭐
