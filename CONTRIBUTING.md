# How to push to PISB GitHub

This guide is for any PISB member who wants to add their work (code, slides, rulebooks, websites) to the [PICT IEEE Student Branch GitHub](https://github.com/PICT-IEEE-Student-Branch). It takes about 5 minutes.

## The one rule

> **Every event or SIG has one repo, named after it. Every year is a folder inside that repo.**
>
> Example: NTH 2026 website → repo **`nth`** → folder **`2026/website/`**

## Step 1: Find where your work goes

| I want to push… | Repo | Folder |
|---|---|---|
| **Credenz website** (frontend + backend) | [`credenz-website`](https://github.com/PICT-IEEE-Student-Branch/credenz-website) | `<year>/frontend/` · `<year>/backend/` |
| **A Credenz event**: platform code, questions, rulebook | the event's own repo: [`xodia`](https://github.com/PICT-IEEE-Student-Branch/xodia) · [`nth`](https://github.com/PICT-IEEE-Student-Branch/nth) · [`datawiz`](https://github.com/PICT-IEEE-Student-Branch/datawiz) · [`enigma`](https://github.com/PICT-IEEE-Student-Branch/enigma) · [`reverse-coding`](https://github.com/PICT-IEEE-Student-Branch/reverse-coding) · [`web-weaver`](https://github.com/PICT-IEEE-Student-Branch/web-weaver) · [`merge-conflict`](https://github.com/PICT-IEEE-Student-Branch/merge-conflict) · [`cretronix`](https://github.com/PICT-IEEE-Student-Branch/cretronix) · [`b-plan`](https://github.com/PICT-IEEE-Student-Branch/b-plan) · [`wallstreet`](https://github.com/PICT-IEEE-Student-Branch/wallstreet) · [`roboliga`](https://github.com/PICT-IEEE-Student-Branch/roboliga) | `<year>/` |
| **CTD website** and sessions | [`ctd`](https://github.com/PICT-IEEE-Student-Branch/ctd) | `<year>/website/` · `<year>/sessions/` |
| **TechRush** rulebook, problem statements, portal | [`techrush`](https://github.com/PICT-IEEE-Student-Branch/techrush) | `<year>/` |
| **SIG** slides, code, notebooks | [`ml-sig`](https://github.com/PICT-IEEE-Student-Branch/ml-sig) · [`frontend-sig`](https://github.com/PICT-IEEE-Student-Branch/frontend-sig) · [`fullstack-sig`](https://github.com/PICT-IEEE-Student-Branch/fullstack-sig) · [`app-dev-sig`](https://github.com/PICT-IEEE-Student-Branch/app-dev-sig) · [`cpp-sig`](https://github.com/PICT-IEEE-Student-Branch/cpp-sig) · [`python-sig`](https://github.com/PICT-IEEE-Student-Branch/python-sig) | `<year>/` |
| **Event photos** | [`memories`](https://github.com/PICT-IEEE-Student-Branch/memories) | add a **view-only** Google Drive link to the README (don't upload the photos) |
| **Research / EPICS proposals** | [`research-and-development`](https://github.com/PICT-IEEE-Student-Branch/research-and-development) · [`epics-in-ieee`](https://github.com/PICT-IEEE-Student-Branch/epics-in-ieee) | see each README |
| **Something new** that isn't listed | Ask the Tech head, or create a repo named after the event (lowercase, hyphens, e.g. `bplan`) with `<year>/` folders inside | — |

## Step 2: Get access (one time)

1. Make a GitHub account if you don't have one.
2. Send your **GitHub username** to the current PISB Tech head. They will invite you to the organisation.
3. Accept the invite from your email, or at [github.com/PICT-IEEE-Student-Branch](https://github.com/PICT-IEEE-Student-Branch).

## Step 3: Push your work

### Option A: no Git needed (slides, PDFs, small projects)

1. Open the repo, e.g. [`nth`](https://github.com/PICT-IEEE-Student-Branch/nth), and click into the year folder (`2026/`).
2. Click **Add file → Upload files**.
3. Drag your files in. Dragging a whole **folder** keeps its structure. To create an empty new folder first, use **Add file → Create new file** and type e.g. `website/README.md` as the name (the `/` creates the folder).
4. Write a short message, e.g. `Add NTH 2026 website`, then click **Commit changes**.

> The browser upload limit is 25 MB per file. For bigger projects, use Option B.

### Option B: Git (code and websites)

```bash
# 1. Download the repo (once)
git clone https://github.com/PICT-IEEE-Student-Branch/nth.git
cd nth

# 2. Copy your project into the right folder
mkdir -p 2026/website
cp -r ~/path/to/your-nth-project/. 2026/website/
# (delete any .git, node_modules or .env that came with it, see the checklist below)

# 3. Save and upload
git add 2026/website
git commit -m "Add NTH 2026 website"
git push
```

**Is your code already in your own GitHub repo?** Copy the files in as shown above; that's the simplest way. If you deploy with **Vercel or Netlify**, point the project at this repo and set *Root Directory* to your folder, e.g. `2026/website`.

## ✅ Checklist before you push

- [ ] **No secrets:** no `.env`, API keys, database URLs or passwords. Commit a `.env.example` with empty values instead. The repos' `.gitignore` already skips `.env`.
- [ ] **No junk:** no `node_modules/`, `venv/`, `__pycache__/`, `.next/` or build folders.
- [ ] **No personal data:** no registration sheets, participant lists, leaderboards with names, phone numbers or personal emails.
- [ ] **No live answers:** quiz and hunt answers (NTH, Enigma, Reverse Coding…) go in only **after** the event is over.
- [ ] **A README in your folder:** what it is, how to run it, how it was deployed, and who built it.
- [ ] **Update the index:** in the repo's README, change *Coming soon* to a link to your folder.

## Need help?

Ask the current PISB Tech head, or email [ieee.pisb@gmail.com](mailto:ieee.pisb@gmail.com).
