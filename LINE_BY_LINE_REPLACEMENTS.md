# EXACT LINE-BY-LINE REPLACEMENTS IN adastra.html

## How to Use This File
1. Open `adastra.html` in VS Code
2. Use Ctrl+G to go to specific lines
3. Use Ctrl+H for Find & Replace
4. Follow the patterns below

---

## SECTION 1: COMPANY INFO

### Title & Meta Description (Lines 8-9)

**FIND:**
```html
<title>Ad Astra | To The Stars</title>
<meta name="description" content="Ad Astra is a premier game development studio pushing the boundaries of interactive entertainment. Creators of Project Nebula and Void Walker.">
```

**REPLACE WITH:**
```html
<title>YOUR_COMPANY_NAME | YOUR_TAGLINE</title>
<meta name="description" content="YOUR_COMPANY_NAME is YOUR_DESCRIPTION. Creators of GAME1 and GAME2.">
```

**EXAMPLE:**
```html
<title>Cosmic Games | Creating Universes</title>
<meta name="description" content="Cosmic Games is an indie game studio creating immersive experiences. Creators of StarQuest and Void Runner.">
```

---

### Logo Text in Navbar (Line ~85)

**FIND:**
```html
<span class="font-display font-bold text-xl tracking-wider uppercase hidden sm:block">AD ASTRA</span>
```

**REPLACE WITH:**
```html
<span class="font-display font-bold text-xl tracking-wider uppercase hidden sm:block">YOUR_COMPANY_NAME</span>
```

---

## SECTION 2: GAME CARDS (Lines ~195-290)

### Game 1: PROJECT NEBULA

**FIND (Lines ~200-210):**
```html
<article class="group relative aspect-[3/4] overflow-hidden rounded-lg bg-gray-900 cursor-pointer card-hover">
    <img src="https://images.unsplash.com/photo-1614728853913-1e2203d9d73d?q=80&w=1600&auto=format&fit=crop" alt="Project Nebula" class="w-full h-full object-cover transition-transform duration-700 ease-out opacity-80 group-hover:opacity-100">
    ...
    <h3 class="font-display font-black text-3xl leading-none mb-2">PROJECT<br>NEBULA</h3>
    <p class="text-gray-400 text-sm mb-4 line-clamp-2 opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">Explore the outer rims of the galaxy in this open-world survival odyssey.</p>
```

**REPLACE WITH:**
```html
<article class="group relative aspect-[3/4] overflow-hidden rounded-lg bg-gray-900 cursor-pointer card-hover">
    <img src="YOUR_GAME1_IMAGE_URL" alt="GAME1_NAME" class="w-full h-full object-cover transition-transform duration-700 ease-out opacity-80 group-hover:opacity-100">
    ...
    <h3 class="font-display font-black text-3xl leading-none mb-2">GAME1<br>NAME</h3>
    <p class="text-gray-400 text-sm mb-4 line-clamp-2 opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">YOUR_GAME1_DESCRIPTION</p>
```

### Game 2: VOID WALKER (Lines ~215-225)

**FIND:**
```html
<img src="https://images.unsplash.com/photo-1614728263952-84ea256f9679?q=80&w=1600&auto=format&fit=crop" alt="Void Walker"...
<h3 class="font-display font-black text-3xl leading-none mb-2">VOID<br>WALKER</h3>
<p class="text-gray-400 text-sm mb-4 opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">A narrative-driven VR experience through the dimensions of time and space.</p>
```

**REPLACE WITH:**
```html
<img src="YOUR_GAME2_IMAGE_URL" alt="GAME2_NAME"...
<h3 class="font-display font-black text-3xl leading-none mb-2">GAME2<br>NAME</h3>
<p class="text-gray-400 text-sm mb-4 opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">YOUR_GAME2_DESCRIPTION</p>
```

### Game 3: STARLIGHT CHRONICLES (Lines ~230-240)

**FIND:**
```html
<img src="https://images.unsplash.com/photo-1596395811779-7a5247960fc0?q=80&w=1600&auto=format&fit=crop" alt="Starlight Chronicles"...
<h3 class="font-display font-black text-3xl leading-none mb-2">STARLIGHT<br>CHRONICLES</h3>
<p class="text-gray-400 text-sm mb-4 opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">A tactical strategy game set during the first interstellar war.</p>
```

**REPLACE WITH:**
```html
<img src="YOUR_GAME3_IMAGE_URL" alt="GAME3_NAME"...
<h3 class="font-display font-black text-3xl leading-none mb-2">GAME3<br>NAME</h3>
<p class="text-gray-400 text-sm mb-4 opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">YOUR_GAME3_DESCRIPTION</p>
```

---

## SECTION 3: NEWS/TRANSMISSIONS (Lines ~280-310)

### News Item 1 (Lines ~285-290)

**FIND:**
```html
<span class="text-brand-orange text-xs font-bold uppercase tracking-wider">Studio Update</span>
<h4 class="font-bold text-lg mt-2 leading-tight group-hover:underline decoration-brand-orange underline-offset-4">Ad Astra at Gamescom: The Future of Space</h4>
<span class="text-xs text-gray-500 mt-2 block">Oct 14, 2025</span>
```

**REPLACE WITH:**
```html
<span class="text-brand-orange text-xs font-bold uppercase tracking-wider">NEWS_CATEGORY</span>
<h4 class="font-bold text-lg mt-2 leading-tight group-hover:underline decoration-brand-orange underline-offset-4">YOUR_NEWS_TITLE</h4>
<span class="text-xs text-gray-500 mt-2 block">YOUR_DATE</span>
```

Also replace the image URL in the same news item:
**FIND:**
```html
<img src="https://images.unsplash.com/photo-1614728263952-84ea256f9679?q=80&w=800&auto=format&fit=crop"
```

**REPLACE WITH:**
```html
<img src="YOUR_NEWS1_IMAGE_URL"
```

### News Items 2-4
Repeat the same process for items at:
- Item 2: ~295-300 (Image: `photo-1541873676...`)
- Item 3: ~305-310 (Image: `photo-1517976487492...`)
- Item 4: ~315-320 (Image: `photo-1590907047706...`)

---

## SECTION 4: FOOTER (Lines ~335-375)

### Copyright Notice (Line ~370)

**FIND:**
```html
<p>&copy; 2026 Ad Astra Studios. All Rights Reserved.</p>
```

**REPLACE WITH:**
```html
<p>&copy; 2026 YOUR_COMPANY_NAME. All Rights Reserved.</p>
```

### Trademark Notice (Lines ~371-373)

**FIND:**
```html
<p class="text-center md:text-right max-w-lg">
    "Project Nebula", "Void Walker", "Ad Astra", and the Ad Astra logo are trademarks or registered trademarks of Ad Astra Studios.
</p>
```

**REPLACE WITH:**
```html
<p class="text-center md:text-right max-w-lg">
    "GAME1", "GAME2", "GAME3", and the YOUR_COMPANY_NAME logo are trademarks or registered trademarks of YOUR_COMPANY_NAME.
</p>
```

### Social Media Links (Lines ~355-365)

**FIND:**
```html
<a href="#" class="hover:text-white transition-colors"><i class="fab fa-twitter text-xl"></i></a>
<a href="#" class="hover:text-white transition-colors"><i class="fab fa-instagram text-xl"></i></a>
<a href="#" class="hover:text-white transition-colors"><i class="fab fa-facebook-f text-xl"></i></a>
<a href="#" class="hover:text-white transition-colors"><i class="fab fa-linkedin-in text-xl"></i></a>
<a href="#" class="hover:text-white transition-colors"><i class="fab fa-youtube text-xl"></i></a>
```

**REPLACE WITH:**
```html
<a href="https://twitter.com/YOUR_HANDLE" class="hover:text-white transition-colors"><i class="fab fa-twitter text-xl"></i></a>
<a href="https://instagram.com/YOUR_HANDLE" class="hover:text-white transition-colors"><i class="fab fa-instagram text-xl"></i></a>
<a href="https://facebook.com/YOUR_PAGE" class="hover:text-white transition-colors"><i class="fab fa-facebook-f text-xl"></i></a>
<a href="https://linkedin.com/company/YOUR_NAME" class="hover:text-white transition-colors"><i class="fab fa-linkedin-in text-xl"></i></a>
<a href="https://youtube.com/@YOUR_CHANNEL" class="hover:text-white transition-colors"><i class="fab fa-youtube text-xl"></i></a>
```

---

## SECTION 5: COLORS (Lines ~20-26)

**FIND:**
```javascript
colors: {
    brand: {
        orange: '#33e1ff', // Ad Astra Cyan
        dark: '#050508',   // Deep Space Black
        gray: '#1f1f1f',
        light: '#e0e0e0'
    }
}
```

**REPLACE WITH:**
```javascript
colors: {
    brand: {
        orange: '#YOUR_PRIMARY_COLOR', // Your brand color
        dark: '#YOUR_DARK_COLOR',      // Your dark background
        gray: '#YOUR_GRAY_COLOR',
        light: '#YOUR_LIGHT_COLOR'
    }
}
```

**EXAMPLE:**
```javascript
colors: {
    brand: {
        orange: '#FF6B35', // Cosmic Orange
        dark: '#0A0E27',   // Deep Blue-Black
        gray: '#1F2937',
        light: '#F0F9FF'
    }
}
```

---

## SECTION 6: JAVASCRIPT API URL (Line ~350)

**FIND:**
```javascript
// CUSTOMIZE THIS: Change to your backend URL when deployed
const API_BASE = 'http://localhost:5000';
```

**REPLACE WITH (Development):**
```javascript
const API_BASE = 'http://localhost:5000';
```

**REPLACE WITH (Production):**
```javascript
const API_BASE = 'https://your-backend-domain.com';
```

**EXAMPLES:**
```javascript
// Heroku
const API_BASE = 'https://your-app-name.herokuapp.com';

// Railway
const API_BASE = 'https://your-app-name.up.railway.app';

// Custom domain
const API_BASE = 'https://api.yourstudio.com';
```

---

## SECTION 7: BACKGROUND IMAGES (Lines ~24, ~30)

### Hero Background (Line ~24)

**FIND:**
```javascript
'hero-pattern': "linear-gradient(to bottom, rgba(0,0,0,0.3), rgba(0,0,0,0.8)), url('https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=2568&auto=format&fit=crop')"
```

**REPLACE WITH:**
```javascript
'hero-pattern': "linear-gradient(to bottom, rgba(0,0,0,0.3), rgba(0,0,0,0.8)), url('YOUR_HERO_IMAGE_URL')"
```

### Join Section Background (Line ~25)

**FIND:**
```javascript
'join-pattern': "linear-gradient(to right, rgba(0,0,0,0.9), rgba(0,0,0,0.4)), url('https://images.unsplash.com/photo-1446776811953-b23d57bd21aa?q=80&w=2301&auto=format&fit=crop')"
```

**REPLACE WITH:**
```javascript
'join-pattern': "linear-gradient(to right, rgba(0,0,0,0.9), rgba(0,0,0,0.4)), url('YOUR_JOIN_IMAGE_URL')"
```

---

## IMAGE URL REFERENCE TABLE

| Purpose | Current URL | Replace With |
|---------|-------------|--------------|
| Game 1 Card | `photo-1614728853913...` | YOUR_GAME1_COVER |
| Game 2 Card | `photo-1614728263952...` | YOUR_GAME2_COVER |
| Game 3 Card | `photo-1596395811779...` | YOUR_GAME3_COVER |
| News 1 | `photo-1614728263952...` | YOUR_NEWS1_IMAGE |
| News 2 | `photo-1541873676...` | YOUR_NEWS2_IMAGE |
| News 3 | `photo-1517976487492...` | YOUR_NEWS3_IMAGE |
| News 4 | `photo-1590907047706...` | YOUR_NEWS4_IMAGE |
| Hero BG | `photo-1451187580459...` | YOUR_HERO_IMAGE |
| Join BG | `photo-1446776811953...` | YOUR_JOIN_IMAGE |

---

## BULK FIND & REPLACE (Quick Method)

### Replace All Unplash Images at Once

Use **Find & Replace** (Ctrl+H) with Regex:

**FIND (Regex):**
```
https://images\.unsplash\.com/photo-[a-zA-Z0-9\-?=&.]+
```

Check "Use Regular Expression" box, then replace each one manually by clicking through.

---

## Common Replacements Quick Copy-Paste

```html
<!-- Company Name -->
Ad Astra → YOUR_COMPANY_NAME

<!-- Game Names -->
PROJECT NEBULA → GAME1_NAME
VOID WALKER → GAME2_NAME
STARLIGHT CHRONICLES → GAME3_NAME

<!-- Copyright Year -->
2026 → CURRENT_YEAR

<!-- Color Hex Codes -->
#33e1ff → YOUR_PRIMARY_COLOR
#050508 → YOUR_DARK_COLOR
```

---

## Testing Your Changes

After each replacement:
1. Save file (Ctrl+S)
2. Refresh browser (F5)
3. Check that text/image updated
4. Verify styling looks correct

---

## Useful VS Code Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl+H | Open Find & Replace |
| Ctrl+G | Go to line number |
| Ctrl+F | Find text |
| Ctrl+Shift+F | Find in all files |
| Alt+Enter | Select all occurrences |
| Ctrl+D | Select next occurrence |

---

Done! All replacements are now line-specific and easy to locate.
