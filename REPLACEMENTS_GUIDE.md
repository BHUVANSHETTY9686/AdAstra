# TEXT & IMAGE REPLACEMENT GUIDE

## Where to Replace Text

### 1. **Company Information**

**File:** `adastra.html`

| What to Replace | Line/Location | Replace With |
|---|---|---|
| `AD ASTRA` (in navbar) | Line ~85 | Your studio name |
| `To The Stars` (in title) | Line ~8 | Your tagline |
| `Ad Astra \| To The Stars` (in title) | Line ~8 | Your company name |
| `Ad Astra is a premier game...` (meta description) | Line ~9 | Your description |

### 2. **Game Names & Descriptions**

**File:** `adastra.html` - Lines ~200-290 (Games Section)

```html
<!-- REPLACE THESE 3 GAME CARDS -->

<!-- Game 1 -->
<h3 class="font-display font-black text-3xl">PROJECT NEBULA</h3>
<!-- Change "PROJECT NEBULA" to your game name -->

<p class="text-gray-400 text-sm">Explore the outer rims of the galaxy...</p>
<!-- Change description -->

<!-- Game 2 -->
<h3 class="font-display font-black text-3xl">VOID WALKER</h3>
<!-- Change "VOID WALKER" to your game name -->

<!-- Game 3 -->
<h3 class="font-display font-black text-3xl">STARLIGHT CHRONICLES</h3>
<!-- Change "STARLIGHT CHRONICLES" to your game name -->
```

### 3. **Contact & Legal Info**

**File:** `adastra.html` - Footer Section (Line ~340)

```html
<!-- Footer Copyright -->
<p>&copy; 2026 Ad Astra Studios. All Rights Reserved.</p>
<!-- Change "2026" to current year and "Ad Astra Studios" to your name -->

<!-- Trademark Notice -->
<p>"Project Nebula", "Void Walker", "Ad Astra"...</p>
<!-- Replace with your game names and studio name -->
```

### 4. **Social Media Links**

**File:** `adastra.html` - Footer (Line ~320)

```html
<a href="#" class="hover:text-white...">
    <i class="fab fa-twitter text-xl"></i>
</a>
<!-- Replace all "#" with your social media URLs -->
```

Locations to update:
- `fab fa-twitter` → Your Twitter URL
- `fab fa-instagram` → Your Instagram URL
- `fab fa-facebook-f` → Your Facebook URL
- `fab fa-linkedin-in` → Your LinkedIn URL
- `fab fa-youtube` → Your YouTube URL

### 5. **News/Transmissions**

**File:** `adastra.html` - Lines ~280-310

```html
<!-- NEWS ITEM 1 -->
<span class="text-brand-orange">Studio Update</span>
<h4>Ad Astra at Gamescom: The Future of Space</h4>
<span>Oct 14, 2025</span>

<!-- NEWS ITEM 2 -->
<span class="text-brand-orange">Community</span>
<h4>Fan Art Feature: Nebula Explorers</h4>

<!-- NEWS ITEM 3 -->
<span class="text-brand-orange">Recruitment</span>
<h4>Welcoming our new VFX Director</h4>

<!-- NEWS ITEM 4 -->
<span class="text-brand-orange">Inside Ad Astra</span>
<h4>Building the Sounds of the Void</h4>
```

Update each news item's category, title, and date.

---

## Where to Replace Images

All image URLs are in `adastra.html`. Use Find & Replace to update them:

### **1. Hero Background**
```
OLD: background: linear-gradient(...), url('https://images.unsplash.com/photo-1451187580459-43490279c0fa?...')
NEW: Your hero image URL
```
Location: Line ~24 in Tailwind config

### **2. Game Cards** (Lines ~195-290)

```html
<!-- GAME 1: PROJECT NEBULA -->
<img src="https://images.unsplash.com/photo-1614728853913-1e2203d9d73d?q=80&w=1600&auto=format&fit=crop">
<!-- Replace with your Game 1 cover image -->

<!-- GAME 2: VOID WALKER -->
<img src="https://images.unsplash.com/photo-1614728263952-84ea256f9679?q=80&w=1600&auto=format&fit=crop">
<!-- Replace with your Game 2 cover image -->

<!-- GAME 3: STARLIGHT CHRONICLES -->
<img src="https://images.unsplash.com/photo-1596395811779-7a5247960fc0?q=80&w=1600&auto=format&fit=crop">
<!-- Replace with your Game 3 cover image -->
```

### **3. News/Transmissions Images** (Lines ~280-310)

```html
<!-- NEWS 1 -->
<img src="https://images.unsplash.com/photo-1614728263952-84ea256f9679?...">

<!-- NEWS 2 -->
<img src="https://images.unsplash.com/photo-1541873676-a18131494184?...">

<!-- NEWS 3 -->
<img src="https://images.unsplash.com/photo-1517976487492-5750f3195933?...">

<!-- NEWS 4 -->
<img src="https://images.unsplash.com/photo-1590907047706-ee9c0f3b4c3c?...">
```

Replace each with your own news/screenshot images.

### **4. Join Section Background**
```
OLD: url('https://images.unsplash.com/photo-1446776811953-b23d57bd21aa?...')
NEW: Your join/careers background image
```

---

## Where to Configure Backend Settings

### **1. Backend API URL**
**File:** `adastra.html` - Line ~350

```javascript
// CUSTOMIZE THIS: Change to your backend URL when deployed
const API_BASE = 'http://localhost:5000';
```

Change `localhost:5000` to:
- Local: `http://localhost:5000` (development)
- Heroku: `https://your-app-name.herokuapp.com`
- Railway: `https://your-app-name.up.railway.app`
- Other: Your backend URL

### **2. Environment Variables**
**File:** `.env`

Create `.env` file from `.env.example`:

```env
# MongoDB Connection
MONGODB_URI=mongodb+srv://USERNAME:PASSWORD@cluster.mongodb.net/adastra-studio

# Email Service (Gmail recommended)
SMTP_USER=admin@yourstudio.com
SMTP_PASS=your-app-password

# Admin email
ADMIN_EMAIL=admin@yourstudio.com

# Server
PORT=5000
```

### **3. Job Postings**
**File:** `server/server.js` - Line ~110

Replace the hardcoded jobs array with your actual job data:

```javascript
const jobs = [
  {
    id: '1',
    title: 'Senior Game Programmer',
    department: 'Engineering',
    // ... more fields
  }
];
```

Later, replace this with MongoDB queries (see documentation in SETUP_GUIDE.md).

---

## Brand Colors to Customize

**File:** `adastra.html` - Lines ~20-25 (Tailwind config)

```javascript
colors: {
  brand: {
    orange: '#33e1ff',  // CHANGE THIS: Your primary brand color
    dark: '#050508',    // CHANGE THIS: Your dark theme color
    gray: '#1f1f1f',    // CHANGE THIS: Your gray tone
    light: '#e0e0e0'    // CHANGE THIS: Your light tone
  }
}
```

Search for these colors in the file and replace:
- `#33e1ff` → Your primary color (appears in buttons, links, accents)
- `#050508` → Your background color

---

## Form Endpoints (Already Configured)

Your backend will handle these automatically once configured:

```
POST /api/contact → Contact form submissions
POST /api/newsletter/subscribe → Newsletter signups
GET /api/jobs → Fetch job listings
POST /api/jobs/apply → Job applications
GET /api/games → Fetch game listings
```

No changes needed here unless you customize the API structure.

---

## Quick Checklist

- [ ] Replace company name (3 places)
- [ ] Replace game names (3 game cards)
- [ ] Update all image URLs (7 images total)
- [ ] Update social media links (5 links)
- [ ] Replace news items (4 items)
- [ ] Set MongoDB URI in `.env`
- [ ] Set email credentials in `.env`
- [ ] Update `API_BASE` URL for production
- [ ] Replace brand colors
- [ ] Update footer copyright year

---

## File Summary

**Frontend:**
- `adastra.html` - Main website file (update text, images, colors, API URL)

**Backend:**
- `server/server.js` - Express server (update hardcoded data with DB queries)
- `server/models/*.js` - Database schemas (add fields as needed)

**Config:**
- `.env` - Environment variables (set database, email, server settings)
- `package.json` - Dependencies (no changes usually needed)

---

## Next Steps

1. Update all text and images in `adastra.html`
2. Create `.env` file with your MongoDB and email settings
3. Run `npm install` to install dependencies
4. Run `npm run dev` to start backend
5. Test forms and API calls
6. Deploy backend to Heroku/Railway/etc
7. Update `API_BASE` URL for production
8. Deploy frontend to Netlify/Vercel/etc
