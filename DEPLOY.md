# How to Deploy Your Portfolio for Free (www.mynulislam.de)

Follow these steps to put your site online **for free** and use your domain **www.mynulislam.de**.

---

## Before You Start

1. **Add your content** in the project folder:
   - **Profile photo:** Save your photo as `profile.jpg` in the same folder as `index.html`.
   - **Resume:** Save your PDF as `resume.pdf` in the same folder.
   - **Links:** In `index.html`, replace:
     - `YOUR_EMAIL@example.com` → your real email
     - `YOUR_WHATSAPP_NUMBER` → your WhatsApp number (e.g. `491234567890` for Germany, no + or spaces)
     - `YOUR_LINKEDIN_USERNAME` → your LinkedIn username (e.g. `mynulislam`)
     - `YOUR_GITHUB_USERNAME` → your GitHub username

2. **GitHub account:** Create one at [github.com](https://github.com) if you don’t have it.

3. **Domain:** You already have **www.mynulislam.de**. You will only change DNS settings at the place where you bought the domain (e.g. Strato, IONOS, Namecheap, etc.).

---

## Option A: Deploy with GitHub Pages (recommended, free)

### Step 1: Install Git (if needed)

- Download: [https://git-scm.com/download/win](https://git-scm.com/download/win)
- Install with default options.

### Step 2: Create a new repository on GitHub

1. Go to [https://github.com/new](https://github.com/new).
2. **Repository name:** e.g. `portfolio` or `mynulislam.de`.
3. Choose **Public**.
4. Do **not** add README, .gitignore, or license (you already have files).
5. Click **Create repository**.

### Step 3: Upload your website to GitHub

Open **PowerShell** or **Command Prompt**, then run:

```powershell
cd "c:\Users\mynul\Documents\Portfolio website"
git init
git add index.html styles.css script.js profile.jpg resume.pdf
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/portfolio.git
git push -u origin main
```

Replace `YOUR_GITHUB_USERNAME` with your GitHub username and `portfolio` with your repo name if different.

If Git asks for login, use your GitHub username and a **Personal Access Token** as password (GitHub → Settings → Developer settings → Personal access tokens → Generate new token).

### Step 4: Turn on GitHub Pages

1. On GitHub, open your repository.
2. Click **Settings** → in the left menu click **Pages**.
3. Under **Source** choose **Deploy from a branch**.
4. Under **Branch** select `main` and folder **/ (root)**.
5. Click **Save**.
6. Wait 1–2 minutes. Your site will be at:  
   `https://YOUR_GITHUB_USERNAME.github.io/portfolio/`  
   (or `https://YOUR_GITHUB_USERNAME.github.io/` if the repo is named `YOUR_GITHUB_USERNAME.github.io`).

### Step 5: Use your domain www.mynulislam.de

1. In the same **Pages** settings, find **Custom domain**.
2. Type: **www.mynulislam.de**
3. Click **Save**.
4. Wait until it shows: “DNS check successful” or similar (can take a few minutes).

### Step 6: Point your domain to GitHub (DNS)

Where you manage **mynulislam.de** (e.g. Strato, IONOS, Namecheap):

1. Open **DNS** or **Domain management**.
2. Add or edit a **CNAME** record:
   - **Name/Host:** `www`
   - **Value/Target:** `YOUR_GITHUB_USERNAME.github.io`  
     (replace with your real GitHub username)
   - **TTL:** 3600 or default.
3. Save.

If the provider asks for the “apex” domain (mynulislam.de without www), you can add an **A** record pointing to GitHub’s IPs (see [GitHub’s custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)), but **www** with CNAME is enough for **www.mynulislam.de**.

### Step 7: Wait and test

- DNS can take from 5 minutes up to 24 hours.
- Then open **https://www.mynulislam.de** in your browser.

---

## Option B: Deploy with Netlify (no Git needed, drag & drop)

1. Go to [https://www.netlify.com](https://www.netlify.com) and create a free account.
2. Drag and drop your **Portfolio website** folder (the one that contains `index.html`) onto the Netlify “Deploy” area.
3. Netlify will give you a URL like `random-name.netlify.app`.
4. To use **www.mynulislam.de**:
   - In Netlify: **Domain settings** → **Add custom domain** → enter **www.mynulislam.de**.
   - At your domain provider: add a **CNAME** for `www` pointing to `random-name.netlify.app` (Netlify will show the exact value).

---

## Checklist

- [ ] Replaced email, WhatsApp, LinkedIn, and GitHub in `index.html`
- [ ] Added `profile.jpg` and `resume.pdf`
- [ ] Chose Option A (GitHub Pages) or B (Netlify)
- [ ] Followed all steps for that option
- [ ] Set DNS CNAME for **www** to GitHub or Netlify
- [ ] Opened **https://www.mynulislam.de** and checked the site

If something doesn’t work, say which step you’re on and what you see (e.g. “Git says permission denied” or “DNS check failed”), and we can fix it step by step.
