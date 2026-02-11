# 🚀 Redeploy Nervestack Website to GitHub Pages

## ✅ Changes Pushed to GitHub

Your website files are now updated and pushed to: https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE

**Updated:**
- Download links now point to v2.0.0 GitHub release assets
- NSL.exe link: `https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/releases/download/v2.0.0/NSL.exe`
- VS Code extension link: `https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/releases/download/v2.0.0/Nervestack-2.0.0.vsix`

---

## 📋 Next Steps: Configure GitHub Pages

### Option 1: Deploy from `Nervestack-website` folder (Recommended)

1. Go to: https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/settings/pages

2. Under **Source**:
   - Branch: Select **main**
   - Folder: Select **/Nervestack-website**
   - Click **Save**

3. Wait 1-2 minutes for deployment

4. Your site will be live at:
   ```
   https://adividan1012.github.io/Nervestack-Labs/
   ```

### Option 2: Deploy from root with custom workflow

If you want the site at the root URL without the `/Nervestack-website` path, you'll need to either:
- Move the website files to the root directory, OR
- Create a custom GitHub Actions workflow

---

## ⚡ Quick Deploy (Recommended)

**Just follow these 3 steps:**

1. **Open Settings**: https://github.com/ADIVIDAN1012/Nervestack-Code-Engine-BCE/settings/pages

2. **Configure**:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/Nervestack-website**

3. **Save** and wait 1-2 minutes

---

## 🔍 Verify Deployment

Once deployed, check:
- ✅ Site loads: https://adividan1012.github.io/Nervestack-Labs/
- ✅ Download buttons work
- ✅ Styling looks correct
- ✅ Images load properly

---

## 🔄 Future Updates

To update the website in the future:

```bash
cd c:\Users\aadit\OneDrive\Desktop\project_2_Nervestack

# Make changes to Nervestack-website/index.html or style.css

git add Nervestack-website/
git commit -m "Update website"
git push origin main
```

GitHub will automatically redeploy within 1-2 minutes!

---

**Your website is ready to go live! 🎉**
