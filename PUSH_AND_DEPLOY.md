# Push and Deploy FastCast Landing Page

## ✅ What's Ready

Your landing page is created and committed locally at:
`~/Desktop/podcast-speed-trainer/`

**Files added:**
- `index.html` - Main landing page
- `1-Now-Playing-2.4x-Speed.png`
- `2-Statistics-7h-33m.png`
- `3-Podcast-Library-Queue.png`
- `4-Settings-Training-Difficulty.png`
- `5-Milestone-Celebration-3.0x.png`

## 🚀 Step 1: Push to GitHub

Run these commands in Terminal:

```bash
cd ~/Desktop/podcast-speed-trainer
git push origin main
```

**If you get an authentication error:**

### Option A: Use GitHub Desktop (Easiest)
1. Open GitHub Desktop app
2. File → Add Local Repository
3. Choose: `~/Desktop/podcast-speed-trainer`
4. Click "Push origin"

### Option B: Use Personal Access Token
1. Go to GitHub.com → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token with `repo` scope
3. Run:
   ```bash
   cd ~/Desktop/podcast-speed-trainer
   git remote set-url origin https://YOUR_TOKEN@github.com/randhirv/podcast-speed-trainer.git
   git push origin main
   ```

### Option C: Use SSH (If configured)
```bash
cd ~/Desktop/podcast-speed-trainer
git remote set-url origin git@github.com:randhirv/podcast-speed-trainer.git
git push origin main
```

---

## 🌐 Step 2: Enable GitHub Pages

1. Go to: https://github.com/randhirv/podcast-speed-trainer
2. Click **Settings** tab
3. Click **Pages** in left sidebar
4. Under "Source":
   - Select: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
5. Click **Save**

GitHub will show: "Your site is ready to be published at https://randhirv.github.io/podcast-speed-trainer/"

Wait 1-2 minutes for deployment.

---

## ✏️ Step 3: Add Your TestFlight Link

Once your TestFlight build is approved for external testing:

1. Get your public TestFlight link from App Store Connect
   - Format: `https://testflight.apple.com/join/ABC123XYZ`

2. Edit `index.html` line 114:
   ```html
   <!-- Change this line: -->
   <a href="YOUR_TESTFLIGHT_LINK_HERE" class="cta-button">Join TestFlight Beta</a>

   <!-- To this: -->
   <a href="https://testflight.apple.com/join/YOUR_CODE" class="cta-button">Join TestFlight Beta</a>
   ```

3. Commit and push:
   ```bash
   cd ~/Desktop/podcast-speed-trainer
   git add index.html
   git commit -m "Add TestFlight public link"
   git push origin main
   ```

---

## 🎉 Your Landing Page Will Be Live At:

### https://randhirv.github.io/podcast-speed-trainer/

Share this link:
- On Twitter/X
- Reddit (r/podcasts, r/SideProject)
- Product Hunt
- Indie Hackers
- Your personal network

---

## 📋 Checklist

- [ ] Push code to GitHub (`git push origin main`)
- [ ] Enable GitHub Pages in repo settings
- [ ] Wait 1-2 minutes for deployment
- [ ] Visit landing page to verify it works
- [ ] Upload build to TestFlight
- [ ] Get public TestFlight link after Beta App Review approval
- [ ] Add TestFlight link to index.html
- [ ] Push update to GitHub
- [ ] Share landing page link!

---

## 🐛 Troubleshooting

**Landing page shows 404:**
- Check GitHub Pages is enabled (Settings → Pages)
- Wait 2-3 minutes after pushing
- Check branch is set to `main` (not `master`)

**Screenshots not showing:**
- Make sure .png files are in root directory
- Check file names match exactly in index.html

**TestFlight button doesn't work:**
- Update `YOUR_TESTFLIGHT_LINK_HERE` in index.html
- Make sure TestFlight link starts with `https://testflight.apple.com/join/`

---

Need help? Check the DEPLOYMENT_GUIDE.md for more details!
