# Pharma Leaders Directory (Static Site)

A lightweight, printable **directory of 30 pharmaceutical companies & leaders** (founder/family background, current leader, education, and a short summary).  
Built as static **HTML + CSS** — easy to host on **Amazon S3** with **GitHub Actions**.

## Project Structure
```
pharma-leaders-site/
├── index.html
├── styles.css
├── assets/
│   ├── logos/
│   │   └── placeholder.png
│   └── leaders/
│       └── placeholder.jpg
└── .github/
    └── workflows/
        └── deploy.yml
```

## Edit Content
- Update each company card inside `index.html` (search by the section id like `#sunpharma`, `#cipla`, etc.).
- Replace placeholder images:
  - Company logos → `assets/logos/<yourfile>.png` and update `<img src="assets/logos/...">`
  - Leader photos → `assets/leaders/<yourfile>.jpg` and update `<img src="assets/leaders/...">`
- Tweak colors/layout in `styles.css`.

## Deploy to Amazon S3 via GitHub Actions
1. **Create an S3 bucket** (Static website hosting) in **us-east-1** (or change in `deploy.yml`).
2. **Set GitHub Secrets** in your repo (Settings → Secrets and variables → Actions → New repository secret):
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
3. **Update bucket name** in `.github/workflows/deploy.yml`:
   - Replace `YOUR_BUCKET_NAME` with your actual bucket.
4. **Push to `main` branch** — the workflow auto-syncs to S3.

## Optional S3 Website Settings
- In your S3 bucket → Properties → Static website hosting:
  - Index document: `index.html`
  - (Optional) Error document: `index.html`
- Ensure correct **Bucket Policy** for public read (if you want a public site), or serve via **CloudFront**.

## Local Preview
Just open `index.html` in your browser. No build step required.

## Credits
- Content structure by you, with placeholders for logos and leader photos.
- Add citations in **HTML comments** inside each company card (kept hidden on the page).
