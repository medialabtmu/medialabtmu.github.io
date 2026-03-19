# TMU Multimedia Research Laboratory Website

Static site built with [Hugo](https://gohugo.io/) and [HugoBlox](https://hugoblox.com/) (formerly Hugo Academic). Hosted on GitHub Pages for free.

---

## Quick Start (First-Time Setup)

### 1. Install Prerequisites

**macOS:**
```bash
brew install hugo node
```

**Windows:**
```bash
choco install hugo-extended nodejs
```

**Linux (Ubuntu/Debian):**
```bash
sudo snap install hugo
sudo apt install nodejs npm
```

Verify Hugo version is 0.145.0 or compatible:
```bash
hugo version
```

### 2. Clone and Run Locally

```bash
git clone https://github.com/YOUR_ORG/mmrl-site.git
cd mmrl-site
hugo mod get          # download theme modules
hugo server -D        # start local dev server with drafts
```

Open http://localhost:1313 in your browser. Changes auto-reload.

### 3. Deploy to GitHub Pages

This is already configured. Just push to `main`:

```bash
git add .
git commit -m "Update site"
git push
```

The GitHub Actions workflow (`.github/workflows/hugo.yaml`) builds and deploys automatically. The site will be live at `https://YOUR_ORG.github.io/mmrl-site/` within about 30 seconds.

**One-time GitHub setup:**
1. Go to your repo on GitHub
2. Settings > Pages > Source: select "GitHub Actions"
3. That's it. The workflow handles the rest.

### 4. Custom Domain (Optional, ~$15 CAD/year)

1. Buy a domain (e.g., `mmrl.ca`) from any registrar (Namecheap, Cloudflare, etc.)
2. In your DNS settings, add a CNAME record: `www` -> `YOUR_ORG.github.io`
3. In GitHub repo: Settings > Pages > Custom domain: enter `mmrl.ca`
4. Update `baseURL` in `hugo.yaml` to `https://mmrl.ca/`

---

## How to Maintain the Site

### Add a New Person

1. Create a folder: `content/people/firstname-lastname/`
2. Copy `_index.md` from an existing person's folder
3. Edit the frontmatter (name, role, bio, social links)
4. Drop in a photo named `avatar.jpg` (square, ~400x400px)
5. Set `user_groups` to one of: `Director`, `Post-Doctoral Fellows`, `Graduate Students`
6. Commit and push

### Move Someone to Alumni

1. Delete their folder from `content/people/`
2. Add an entry to `data/alumni.yaml`
3. Commit and push

### Add a Publication

**Option A: Manual (one at a time)**
1. Create a folder: `content/publications/short-name-2024/`
2. Copy `index.md` from `content/publications/example-paper/`
3. Fill in title, authors, date, venue, abstract, links
4. Commit and push

**Option B: Bulk import from BibTeX**
```bash
pip install academic
academic import --bibtex data/publications.bib
```
This generates one folder per entry. Review, commit, push.

### Add a News Post

1. Create a folder: `content/news/short-title/`
2. Create `index.md` with frontmatter (title, date, summary)
3. Write the post body in Markdown
4. Commit and push

### Add a Project

1. Create a folder: `content/projects/project-name/`
2. Copy `index.md` from `content/projects/example-project/`
3. Fill in the details
4. Optionally add `featured.jpg` for a hero image
5. Commit and push

### Add a Video

Edit `content/videos/_index.md` and add a YouTube embed:
```markdown
### Talk Title

{{</* youtube VIDEO_ID */>}}
```

### Customize Appearance

- Theme colors: edit `assets/scss/custom.scss`
- Site metadata: edit `hugo.yaml`
- Menu items: edit the `menus` section in `hugo.yaml`

---

## File Structure

```
mmrl-site/
├── hugo.yaml                  # Main config (site title, menu, params)
├── go.mod                     # Hugo module dependencies
├── hugoblox.yaml              # HugoBlox version pin
├── .github/workflows/hugo.yaml # Auto-deploy on push
├── assets/scss/custom.scss    # Style overrides
├── data/
│   ├── alumni.yaml            # Alumni table data
│   └── publications.bib       # BibTeX for bulk import
├── content/
│   ├── _index.md              # Homepage (hero, research areas, feeds)
│   ├── people/                # One folder per person
│   │   ├── _index.md          # Section config
│   │   ├── naimul-khan/       # Director profile
│   │   ├── postdoc-example/   # Template - delete when real people added
│   │   └── student-example/   # Template - delete when real people added
│   ├── projects/              # One folder per project
│   ├── publications/          # One folder per paper
│   ├── news/                  # One folder per news post
│   ├── videos/                # Single page with embeds
│   ├── join/                  # Recruitment page
│   └── contact/               # Contact info
└── static/images/             # Site-wide images (logo, etc.)
```

---

## Tips

- **Preview before publishing:** Always run `hugo server -D` locally before pushing.
- **Delegate updates:** Give a student write access to the repo. They can add people/publications through the GitHub web editor without installing anything.
- **Images:** Keep them reasonable in size. 200KB per photo is plenty for the web.
- **Google Scholar link:** Replace `REPLACE_WITH_YOUR_ID` in `content/publications/_index.md` and `content/people/naimul-khan/_index.md` with your actual Google Scholar ID.
