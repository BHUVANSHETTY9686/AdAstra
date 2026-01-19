# Ad Astra Game Studio - Full Stack Setup Guide

## Project Structure
```
adastra-studio/
├── server/
│   ├── server.js                 # Express server
│   ├── config/
│   │   └── database.js           # MongoDB connection
│   ├── models/
│   │   ├── Contact.js            # Contact form model
│   │   ├── JobApplication.js     # Job application model
│   │   ├── Newsletter.js         # Newsletter signup model
│   │   ├── Game.js               # Game listing model
│   │   └── JobPosting.js         # Job posting model
│   ├── routes/
│   │   ├── contact.js            # Contact form routes
│   │   ├── jobs.js               # Job posting & application routes
│   │   ├── newsletter.js         # Newsletter routes
│   │   └── games.js              # Game listing routes
│   └── middleware/
│       └── errorHandler.js       # Error handling
├── public/
│   └── index.html                # Updated with forms
├── .env                          # Environment variables
├── package.json                  # Dependencies
└── README.md                      # Project documentation
```

---

## Step 1: Initialize Node.js Project

```bash
cd d:\CompanySites
npm init -y
npm install express mongoose dotenv cors nodemailer bcryptjs
npm install --save-dev nodemon
```

Update `package.json` scripts:
```json
"scripts": {
  "start": "node server/server.js",
  "dev": "nodemon server/server.js"
}
```

---

## Step 2: Environment Variables (.env)

Create `.env` file in root:
```
# Database
MONGODB_URI=mongodb+srv://YOUR_USERNAME:YOUR_PASSWORD@cluster.mongodb.net/adastra-studio

# Email Service (Gmail, SendGrid, or your provider)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password

# Admin Email (where forms submit to)
ADMIN_EMAIL=admin@adastra-studio.com

# Server
PORT=5000
NODE_ENV=development
CLIENT_URL=http://localhost:3000
```

---

## Step 3: Database Setup (MongoDB)

### Sign Up for MongoDB Atlas:
1. Go to https://www.mongodb.com/cloud/atlas
2. Create a free cluster
3. Create a database user
4. Get connection string and add to `.env`

### Database Collections to Create:
- **contacts** - Contact form submissions
- **jobApplications** - Job applicant data
- **newsletters** - Email subscriptions
- **gameListings** - Your games
- **jobPostings** - Job openings

---

## Step 4: What to Customize

### **Text Replacements in HTML:**

1. **Company Info:**
   - `AD ASTRA` → Your studio name
   - `To The Stars` → Your tagline
   - "Ad Astra Studios" → Your full name
   - Dates (2026) → Current year

2. **Game Names & Descriptions:**
   - `PROJECT NEBULA` → Game 1 name
   - `VOID WALKER` → Game 2 name
   - `STARLIGHT CHRONICLES` → Game 3 name
   - Descriptions in the game cards

3. **Contact Info:**
   - Email addresses in footer
   - Social media links (Twitter, Instagram, etc.)
   - Phone number (add if needed)

4. **Colors:**
   - `#33e1ff` (cyan) → Your brand color
   - `#050508` (dark) → Your dark theme color

### **Image Replacements:**

Replace all image URLs with your own:
```
Location: Game Cards Section
https://images.unsplash.com/photo-1614728853913-1e2203d9d73d?q=80&w=1600&auto=format&fit=crop
→ Replace with: Your Game 1 cover image URL

https://images.unsplash.com/photo-1614728263952-84ea256f9679?q=80&w=800&auto=format&fit=crop
→ Replace with: Your Game 1 screenshot URL
```

All image URLs to replace:
- Game card images (3 games)
- News/transmission images (4 news items)
- Background images (hero, join section)

### **Form Endpoints:**

All forms will POST to:
- `/api/contact` - Contact form
- `/api/jobs/apply` - Job applications
- `/api/newsletter/subscribe` - Newsletter signup
- `/api/games` - Get game listings (GET)
- `/api/jobs` - Get job postings (GET)

---

## Step 5: Important Configuration Points

### Email Service Setup:
For Gmail (easiest):
1. Enable 2-Factor Authentication
2. Generate App Password: https://myaccount.google.com/apppasswords
3. Use the 16-char password in `.env` as `SMTP_PASS`

### Hosting the Backend:
- **Heroku** - Free tier works, use Heroku Postgres/MongoDB Atlas
- **Railway** - Great alternative, pay-as-you-go
- **Render** - Easy deployment
- **AWS/DigitalOcean** - More control

### Frontend Hosting:
- **Netlify** - Drag & drop deployment
- **Vercel** - Optimized for Next.js/React
- **GitHub Pages** - Static hosting
- **Same server** as backend (simpler)

---

## Step 6: API Response Formats

Backend will return JSON responses. Update your frontend to handle:

```javascript
// Contact form success
{
  "success": true,
  "message": "Message sent successfully",
  "data": { "name": "John", "email": "john@example.com" }
}

// Job application success
{
  "success": true,
  "message": "Application submitted",
  "data": { "jobId": "123", "applicantName": "Jane" }
}

// Get games list
{
  "success": true,
  "games": [
    { "id": "1", "name": "Project Nebula", "description": "...", "imageUrl": "..." }
  ]
}

// Get job postings
{
  "success": true,
  "jobs": [
    { "id": "1", "title": "Game Programmer", "department": "Engineering", "location": "Remote" }
  ]
}
```

---

## Step 7: Testing Locally

```bash
# Terminal 1 - Start backend
npm run dev

# Terminal 2 - Open HTML in browser
# Double-click adastra.html or serve with live server
```

Test with browser DevTools → Network tab to see API calls.

---

## Files to Create Next

I'll provide the following files:
1. ✅ `server/server.js` - Main Express app
2. ✅ `server/config/database.js` - MongoDB connection
3. ✅ `server/models/*.js` - Database schemas
4. ✅ `server/routes/*.js` - API endpoints
5. ✅ `package.json` - Dependencies
6. ✅ Updated `index.html` - Forms integrated

Ready to proceed?
