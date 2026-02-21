# Put This Portfolio on GitHub Pages (Quick Steps)

Do these in order. Replace **YOUR_GITHUB_USERNAME** with your real GitHub username everywhere.

---

## 1. Create the repository on GitHub

1. Go to **https://github.com/new**
2. **Repository name:** `portfolio` (or `mynulislam.github.io` if you want the site at `https://mynulislam.github.io`)
3. **Public** → Create repository (don’t add README, .gitignore, or license)

---

## 2. Open PowerShell in your project folder

- In File Explorer go to: `c:\Users\mynul\Documents\Portfolio website`
- **Shift + Right‑click** in the folder → **Open PowerShell window here**

(Or open PowerShell and run: `cd "c:\Users\mynul\Documents\Portfolio website"`)

---

## 3. Run these commands one by one

```powershell
git init
git add index.html styles.css script.js README.md DEPLOY.md .gitignore
git add profile.jpg
git add resume.pdf
```

If `profile.jpg` or `resume.pdf` don’t exist yet, skip those lines (or add them later and run `git add profile.jpg resume.pdf` again).

Then:

```powershell
git commit -m "Portfolio for GitHub Pages"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/portfolio.git
git push -u origin main
```

**Replace** `YOUR_GITHUB_USERNAME` with your GitHub username and `portfolio` with your repo name if you chose a different one.

- If Git asks for **username:** your GitHub username  
- If it asks for **password:** use a **Personal Access Token** (GitHub → Settings → Developer settings → Personal access tokens → Generate new token, tick `repo`).

---

## 4. Turn on GitHub Pages

1. On GitHub, open your repository
2. **Settings** → **Pages** (left sidebar)
3. **Source:** Deploy from a branch
4. **Branch:** `main` → **/ (root)** → **Save**
5. Wait 1–2 minutes

Your site will be at:

- **https://YOUR_GITHUB_USERNAME.github.io/portfolio/**  
  (or **https://YOUR_GITHUB_USERNAME.github.io/** if the repo is named `YOUR_GITHUB_USERNAME.github.io`)

---

## 5. (Optional) Use your domain www.mynulislam.de

1. In **Settings → Pages**, under **Custom domain** type: **www.mynulislam.de** → **Save**
2. At your domain provider (where you bought mynulislam.de), add a **CNAME** record:
   - **Name:** `www`
   - **Target:** `YOUR_GITHUB_USERNAME.github.io`
3. Wait 5–60 minutes for DNS, then open **https://www.mynulislam.de**

Done.
