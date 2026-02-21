## 🚀 Quick Start for GitHub Pages

### 1️⃣ Create a GitHub Repository

```bash
# Initialize git in this folder
git init
git add .
git commit -m "Initial commit: Geospatial Explorer Pro"

# Create a new repository on GitHub (https://github.com/new)
# Copy the repository URL and run:

git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

### 2️⃣ Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under "Source", select **Deploy from a branch**
4. Select branch: **main** 
5. Select folder: **/ (root)**
6. Click **Save**

### 3️⃣ Wait and Access

GitHub will deploy the site automatically. Your site will be live at:
- `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/(index.html)`

That's it! The application will automatically load your data files.

---

## 📋 Before Pushing to GitHub

Make sure you have all these files in your repository folder:

```
✓ index.html              (main application file)
✓ Dov Play Gaz - Sheet1.csv  (location data)
✓ GEO.json              (boundary data)
✓ README.md             (documentation)
✓ .gitignore            (ignore rules)
✓ .nojekyll             (disable Jekyll)
```

## ⚡ How It Works

1. **Auto-Loading**: When you open the site, it automatically fetches:
   - `Dov Play Gaz - Sheet1.csv` → Location markers on the map
   - `GEO.json` → Political boundaries

2. **Offline Capable**: Everything works offline - no external APIs

3. **Interactive**: Use the time slider (1886-2024) to see historical changes

## 🆘 Troubleshooting

**"Files not auto-loading?"**
- Check the browser console (F12 → Console tab)
- Ensure CSV and JSON files are in the same directory as index.html
- Verify filenames match exactly (case-sensitive!)

**"Site shows blank?"**
- Clear browser cache (Ctrl+Shift+Delete)
- Check Console tab for errors
- Make sure your repository is public (or GitHub Pages is enabled)

## 💡 Pro Tips

- Update CSV/GeoJSON files anytime and push to GitHub - website updates automatically
- To test locally: Use a local server instead of opening the HTML file directly
  ```bash
  python -m http.server 8000  # Then open http://localhost:8000
  ```
- Customize the README.md to explain your specific data

---

Success! Your geospatial explorer is now live on GitHub Pages! 🎉
