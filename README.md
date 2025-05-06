# Scalable-Static-Website-with-S3-CloudFlare-GitHub-Action
Host and auto-deploy a static website using S3(free tier) with global CDN and HTTPS via Cloudflare, triggered through GitHub commits.

## Objective
Host and auto-deploy a static website using AWS S3, Cloudflare, and GitHub Actions.

## Tools
- AWS S3 (Free Tier)
- Cloudflare (Free)
- GitHub Actions
- HTML/CSS

## Project Structure
```
index.html
styles.css
.github/
└── workflows/
    └── deploy.yml
```

## Step-by-Step Guide

### Step 1: Create Static Website
Write your HTML and CSS files (`index.html`, `styles.css`).

### Step 2: Create S3 Bucket
- Go to AWS S3 console.
- Create a bucket (disable block public access).
- Enable static website hosting.

### Step 3: Configure Cloudflare
- Register a domain or use existing.
- Add S3 static site endpoint as origin.
- Enable SSL/TLS encryption.

### Step 4: Set GitHub Secrets
In your repo settings:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_S3_BUCKET`

### Step 5: Configure GitHub Actions
`.github/workflows/deploy.yml` syncs files to S3 on every push to `main`.

### Step 6: Push to GitHub
```bash
git init
git remote add origin https://github.com/your-user/static-site.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

### Step 7: Visit Your Site
Use your Cloudflare custom domain with HTTPS.

