# DEPLOYMENT GUIDE - Full Stack Game Studio Website

## Quick Start (Local Testing)

### Step 1: Initialize Project
```bash
cd d:\CompanySites
npm install
```

### Step 2: Create .env file
```bash
# Copy .env.example to .env and fill in values
# Minimum required for testing:
MONGODB_URI=mongodb+srv://user:password@cluster.mongodb.net/adastra-studio
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
ADMIN_EMAIL=admin@yourdomain.com
```

### Step 3: Start Backend
```bash
npm run dev
# Server will run on http://localhost:5000
```

### Step 4: Open Frontend
```bash
# Option 1: Double-click adastra.html
# Option 2: Use Live Server extension in VS Code
# Option 3: Use Python server
python -m http.server 3000
# Then open http://localhost:3000/adastra.html
```

### Step 5: Test Forms
- Try contact form → Check console for API call
- Try newsletter signup → Check console
- Click "View Openings" → Should load jobs from backend

---

## Production Deployment

### Option A: Heroku (Recommended for Beginners)

#### Backend Deployment

1. **Install Heroku CLI**
   ```bash
   # From: https://devcenter.heroku.com/articles/heroku-cli
   # Windows: Download installer and run
   ```

2. **Create Heroku App**
   ```bash
   heroku login
   heroku create your-app-name
   ```

3. **Set Environment Variables**
   ```bash
   heroku config:set MONGODB_URI="your-mongodb-url"
   heroku config:set SMTP_USER="your-email@gmail.com"
   heroku config:set SMTP_PASS="your-app-password"
   heroku config:set ADMIN_EMAIL="admin@yourdomain.com"
   heroku config:set NODE_ENV="production"
   ```

4. **Deploy**
   ```bash
   git add .
   git commit -m "Deploy to Heroku"
   git push heroku main
   # Or: heroku deploy --source=local
   ```

5. **Verify**
   ```bash
   heroku open
   # Should see your API running
   ```

#### Frontend Deployment (Netlify)

1. **Sign up at netlify.com**

2. **Deploy**
   ```bash
   npm install -g netlify-cli
   netlify login
   netlify deploy
   # Select public folder: . (current directory)
   ```

3. **Update API URL**
   - In `adastra.html`, change:
   ```javascript
   const API_BASE = 'https://your-app-name.herokuapp.com';
   ```
   - Redeploy to Netlify

---

### Option B: Railway (Simpler Alternative)

#### Backend Deployment

1. **Create account at railway.app**

2. **Connect GitHub or upload project**

3. **Set Environment Variables** in Railway dashboard

4. **Deploy** - Railway auto-deploys

#### Frontend on Railway

1. **Add `public` folder or serve static files from Express**

2. **Or deploy separately on Vercel/Netlify**

---

### Option C: Self-Hosted (VPS/Dedicated Server)

#### Requirements
- Ubuntu 20.04+ or similar Linux
- Node.js installed
- MongoDB Atlas (free cloud database)
- Domain name (optional)

#### Setup

```bash
# SSH into your server
ssh root@your-server-ip

# Install Node
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt-get install -y nodejs

# Clone your project
git clone https://github.com/yourname/adastra-studio.git
cd adastra-studio

# Install dependencies
npm install

# Create .env file
nano .env
# Paste your environment variables

# Install PM2 (process manager)
npm install -g pm2

# Start server
pm2 start server/server.js --name "adastra-api"
pm2 startup
pm2 save

# Use Nginx as reverse proxy
# (See nginx config below)
```

#### Nginx Configuration

```bash
# Edit /etc/nginx/sites-available/adastra
sudo nano /etc/nginx/sites-available/adastra

# Paste:
server {
    listen 80;
    server_name yourdomain.com;

    location / {
        proxy_pass http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}

# Enable site
sudo ln -s /etc/nginx/sites-available/adastra /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl restart nginx

# Setup SSL (Let's Encrypt)
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d yourdomain.com
```

---

## Database Setup (MongoDB Atlas)

### Step 1: Create Account
- Go to https://www.mongodb.com/cloud/atlas
- Sign up with email

### Step 2: Create Cluster
1. Click "Create" → Select FREE tier
2. Choose region closest to you
3. Wait for cluster creation (2-3 min)

### Step 3: Create Database User
1. Go to "Database Access"
2. Click "Add New Database User"
3. Set username and password
4. Add to all databases

### Step 4: Add IP Whitelist
1. Go to "Network Access"
2. Click "Add IP Address"
3. Select "Allow Access from Anywhere" (for development)
   - Production: Add specific IP

### Step 5: Get Connection String
1. Click "Connect" → "Connect your application"
2. Copy connection string
3. Replace `<username>:<password>` with your credentials
4. Paste into `.env` as `MONGODB_URI`

Example:
```
mongodb+srv://admin:password123@cluster.mongodb.net/adastra-studio?retryWrites=true&w=majority
```

---

## Email Setup (Gmail)

### Step 1: Enable 2-Factor Authentication
1. Go to https://myaccount.google.com/security
2. Turn on "2-Step Verification"

### Step 2: Generate App Password
1. In Google Account, go to "App passwords"
2. Select "Mail" and "Windows Computer"
3. Google generates 16-character password
4. Copy and paste into `.env` as `SMTP_PASS`

### Step 3: Test
```javascript
// In server/server.js, add test:
const nodemailer = require('nodemailer');
const transporter = nodemailer.createTransport({
  host: process.env.SMTP_HOST,
  port: process.env.SMTP_PORT,
  secure: false,
  auth: {
    user: process.env.SMTP_USER,
    pass: process.env.SMTP_PASS
  }
});

transporter.verify((error) => {
  if (error) {
    console.log('❌ Email Error:', error);
  } else {
    console.log('✅ Email Ready');
  }
});
```

---

## Domain Setup (Optional)

### Connect Domain to Frontend (Netlify)
1. In Netlify dashboard → Settings → Domain management
2. Add custom domain
3. Update DNS records at your registrar

### Connect Domain to Backend
- Point `api.yourdomain.com` to your server
- Or use same domain with path routing (`yourdomain.com/api/*`)

---

## Continuous Deployment (GitHub)

### Setup Auto-Deploy

**Heroku with GitHub:**
```bash
# In Heroku dashboard
# Go to Deploy → GitHub
# Connect repo → Enable auto-deploy
```

**Netlify with GitHub:**
```bash
# In Netlify
# Deploy → Connect to Git
# Select repo and branch
# Auto-deploys on push
```

---

## Monitoring & Logging

### Monitor Backend (Heroku)
```bash
heroku logs --tail
```

### Check Server Status
```bash
# SSH into server
pm2 logs adastra-api
pm2 status
```

### Monitor Database
- MongoDB Atlas Dashboard
- View operations, performance, backups

---

## Troubleshooting

### "Cannot reach backend" error
1. Check `API_BASE` URL is correct
2. Backend must be running: `npm run dev`
3. Check firewall/CORS settings
4. Verify `.env` variables

### "MongoDB connection failed"
1. Check `MONGODB_URI` is correct
2. Add your IP to MongoDB Atlas whitelist
3. Verify credentials

### "Email not sending"
1. Verify SMTP credentials
2. Check "Less secure apps" setting (if not using app password)
3. Test with `nodemailer` directly

### Forms submitting but not saving
1. Check backend console for errors
2. Verify database models are correct
3. Test API endpoints with Postman

---

## Security Checklist

- [ ] MongoDB password is strong (16+ chars, mixed case, numbers, symbols)
- [ ] Email app password generated (not actual password)
- [ ] .env file added to `.gitignore`
- [ ] No hardcoded secrets in code
- [ ] CORS whitelist configured (production)
- [ ] SSL/TLS enabled (HTTPS)
- [ ] Rate limiting added to forms
- [ ] Input validation on all endpoints
- [ ] Admin dashboard password protected
- [ ] Database backups enabled

---

## Cost Estimates (Monthly)

| Service | Free Tier | Paid |
|---------|-----------|------|
| MongoDB Atlas | 0.5 GB free | $9-100+ |
| Heroku | Deprecated | $7+ |
| Railway | $5 credit | Pay-as-you-go |
| Netlify | Unlimited | $19+ |
| Vercel | Unlimited | $20+ |
| Gmail API | Unlimited | Free* |

*Total monthly: ~$20-50 for small site

---

## Support Resources

- Heroku Docs: https://devcenter.heroku.com
- Railway Docs: https://docs.railway.app
- MongoDB Docs: https://docs.mongodb.com
- Express Docs: https://expressjs.com
- Nodemailer Docs: https://nodemailer.com
