# Putting this on GitHub

Two ways. **Option A needs no command line** and is the one to use if you just want it live.

---

## Option A — the GitHub website (no terminal)

**1. Make the repository**

Go to [github.com/new](https://github.com/new).

- **Repository name:** `the-turning`
- **Public** (required — GitHub Pages needs it on a free account)
- Leave *"Add a README file"*, *.gitignore* and *license* **unchecked**. This folder already has a README, and adding one would collide.
- Click **Create repository**.

**2. Upload the files**

On the empty repository page, click the link **"uploading an existing file"**.

Unzip the folder I gave you, open it, select **everything inside it** and drag it into the browser:

```
index.html      ← the whole game, one file
README.md
UPLOAD.md
.nojekyll
gameplay.gif
teaser.gif
tools/          ← the level generator and verifier
```

> **Important:** drag the *contents* of the folder, not the folder itself. `index.html` has to sit at the top level of the repository or Pages will not find it.
>
> If `.nojekyll` doesn't appear in your file picker, it's because macOS hides dotfiles — press **⌘ + Shift + .** in Finder to show them. It's a safety file; the site works without it, but include it if you can.

Then scroll down and click **Commit changes**.

**3. Turn on GitHub Pages**

In your repository: **Settings** → **Pages** (left sidebar).

- **Source:** Deploy from a branch
- **Branch:** `main`, folder `/ (root)`
- **Save**

**4. Wait, then collect your link**

Give it one to two minutes. Refresh the Pages settings page and it will show:

```
https://YOUR-USERNAME.github.io/the-turning/
```

That's the link your classmates click. Open it once yourself to confirm it plays.

**5. Put the link in the README**

Back in the repository, click `README.md` → the pencil icon → replace the placeholder on line 6 with your real URL → **Commit changes**.

---

## Option B — the command line

```bash
cd the-turning
git init
git add .
git commit -m "The Turning"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/the-turning.git
git push -u origin main
```

Then do step 3 above to switch Pages on.

If you have the GitHub CLI installed, steps 1 and 2 collapse into one:

```bash
gh repo create the-turning --public --source=. --push
```

---

## What to hand in

| | |
|---|---|
| **Repository link** | `https://github.com/YOUR-USERNAME/the-turning` |
| **Live site link** | `https://YOUR-USERNAME.github.io/the-turning/` |
| **Slide** | `gameplay.gif` dropped onto your slide, with the live link beside it |

---

## If something goes wrong

**The site shows a 404.** Nearly always one of three things: Pages was only just switched on (wait two minutes), the branch/folder in Settings → Pages is wrong, or `index.html` ended up *inside* a subfolder instead of at the root. Open the repository's file list — you should see `index.html` on the first screen, not after clicking into a folder.

**The page loads but is blank.** Open the browser console (⌥⌘I on Mac, F12 on Windows). The game needs no network at all except Google Fonts, so a blank page almost certainly means `index.html` didn't upload fully — re-upload it.

**There's no sound.** Browsers refuse to start audio until you interact with the page. Click once and it fades in. **M** toggles it.

**It's slow on an old laptop.** It handles that itself — the soft shading switches off first, then the pixel density drops. You don't need to do anything.
