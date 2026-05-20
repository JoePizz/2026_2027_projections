# 🚀 Deploy to GitHub Pages - Step by Step

## Prerequisites
- GitHub account
- Git installed on your computer
- The files from this project

## Step 1: Create a New Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: **`hockey-predictions`**
3. Description: "Interactive 2026-27 junior hockey predictions dashboard"
4. Public (so it can be viewed online)
5. Click "Create repository"

## Step 2: Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/hockey-predictions.git
cd hockey-predictions
```

## Step 3: Add Files

Copy these files into your local repo folder:
- `index.html` - The dashboard
- `predictions_data.json` - The player data
- `README.md` - Documentation
- `.gitignore` - Git ignore file

```bash
# On your computer, copy the files to the folder you just cloned
# Then:
git add .
git commit -m "Initial commit: predictions dashboard with 2277 players"
git push origin main
```

## Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (gear icon, top right)
3. Scroll down to **Pages** section (left sidebar)
4. Under "Build and deployment":
   - Source: Select "Deploy from a branch"
   - Branch: Select "main"
   - Folder: Select "/ (root)"
5. Click **Save**

Your site will be live in ~1-2 minutes at:
```
https://YOUR_USERNAME.github.io/hockey-predictions/
```

## Step 5: Share Your Link!

Your dashboard is now live! Share the URL:
- With scouts
- With coaches
- With parents
- On social media

## Updating the Dashboard

To add new predictions or update data:

1. Update `predictions_data.json` with new data
2. Commit and push:
   ```bash
   git add predictions_data.json
   git commit -m "Update predictions for 2026-27 season"
   git push origin main
   ```
3. Changes appear online within ~1 minute

## Tips

- The dashboard works **completely offline** in the browser
- No backend server needed
- Data loads from the JSON file only once
- All filtering/sorting happens in JavaScript

## Troubleshooting

**Site not showing up?**
- Wait 2-3 minutes after enabling Pages
- Check that source is set to "main" branch
- Clear your browser cache

**Data not updating?**
- Make sure you pushed to GitHub
- Clear browser cache (Ctrl+Shift+Delete)
- Hard refresh (Ctrl+F5)

**Styling looks broken?**
- Verify `index.html` is in the root folder
- Check browser console (F12) for errors

---

**Questions?** Check the README.md for more info!
