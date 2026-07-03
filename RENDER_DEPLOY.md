# Render Deployment Instructions

## Quick Deploy to Render (Free HTTPS Hosting)

This project is ready to deploy to Render.com with automatic HTTPS support.

### Step 1: Push Code to GitHub
1. Create a GitHub account if you don't have one: https://github.com/signup
2. Create a new repository: https://github.com/new
3. Initialize git locally:
   ```
   cd c:\Users\nohit\Downloads\flood_project\flood_project
   git init
   git add .
   git commit -m "Initial commit - Flood prediction model"
   git remote add origin https://github.com/YOUR_USERNAME/flood-prediction.git
   git branch -M main
   git push -u origin main
   ```

### Step 2: Deploy to Render
1. Go to https://render.com and sign up (free account)
2. Click "New +" → "Web Service"
3. Connect your GitHub account when prompted
4. Select your `flood-prediction` repository
5. Fill in the deployment settings:
   - **Name**: `flood-prediction-api`
   - **Environment**: Python 3
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
   - **Plan**: Free tier
6. Click "Create Web Service"

Render will deploy your app and provide an HTTPS URL like:
`https://flood-prediction-api.onrender.com`

### Step 3: Update Firebase Frontend
Once your Render URL is deployed (takes ~2-3 minutes), update the Firebase frontend:

Change this line in `public/index.html`:
```
const resp = await fetch('https://cactus-drizzle-finance.ngrok-free.dev/predict',
```

To:
```
const resp = await fetch('https://flood-prediction-api.onrender.com/predict',
```

Then redeploy to Firebase:
```
firebase deploy --only hosting --project raising-waters
```

### That's it!
Your live demo will work perfectly with HTTPS on both Firebase and Render.

---

## Alternative: Use Platform.sh (Even Simpler)
If GitHub is complex, you can also use Platform.sh which has GitHub-less deployment.
