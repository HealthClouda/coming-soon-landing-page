# HealthClouda — Coming Soon Landing Page

**One ID. Every Hospital. For Life.** 🇳🇬

HealthClouda is Nigeria's lifetime health identity infrastructure — a platform connecting university/school clinics to hospitals through digital referrals and a lifetime patient health ID (HCL ID).

This repository contains the "Coming Soon" landing page for HealthClouda, designed to capture early interest ahead of the Ilorin launch.

## Project Structure

```
index.html                    # Complete landing page (HTML + CSS + JS)
.github/workflows/deploy.yml  # GitHub Pages auto-deployment workflow
README.md                     # This file
```

## Updating the Formspree Endpoint

The email capture forms submit to [Formspree](https://formspree.io). To update the endpoint:

1. Create a form at [formspree.io](https://formspree.io)
2. Copy your form endpoint (e.g., `https://formspree.io/f/yourFormId`)
3. In `index.html`, find and replace all instances of:
   ```
   https://formspree.io/f/xreygqbg
   ```
   with your new endpoint (there are 2 forms in the page).

## Deploying to GitHub Pages

### Automatic Deployment (GitHub Actions)

This repo includes a GitHub Actions workflow that automatically deploys to GitHub Pages on every push to `main`.

1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Under **Source**, select **GitHub Actions**
4. The site will deploy automatically on the next push to `main`

### Manual Setup

1. Go to your repository **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose **main** branch and **/ (root)** folder
4. Click **Save**
5. Your site will be live at `https://<username>.github.io/<repo-name>/`

## Connecting a Custom Domain

To use `healthclouda.com.ng`:

1. Go to **Settings → Pages → Custom domain**
2. Enter `healthclouda.com.ng` and click **Save**
3. At your domain registrar, add these DNS records:
   - **A records** (for apex domain):
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **CNAME record** (for `www` subdomain):
     ```
     www → <username>.github.io
     ```
4. Check **Enforce HTTPS** in GitHub Pages settings once DNS propagates
5. Optionally create a `CNAME` file in the repo root containing `healthclouda.com.ng`

## Tech Stack

- Pure HTML, CSS, and JavaScript — no frameworks or build tools
- Google Fonts (Inter)
- Formspree for email capture
- Intersection Observer API for scroll animations
- GitHub Actions for deployment
