# Deployment Guide — Gowtham Portfolio

## Overview

This portfolio is deployed to **GitHub Pages** using an automated CI/CD pipeline via **GitHub Actions**.

## Deployment Architecture

```
Local Development
     ↓ (git push to main)
GitHub Repository
     ↓ (trigger workflow)
GitHub Actions
     ├── Install dependencies (npm install)
     ├── Build production assets (npm run build)
     └── Deploy to gh-pages branch
           ↓
GitHub Pages CDN
     ↓
https://tekigowtham2204.github.io/Gowtham-Portfolio/
```

## GitHub Pages Configuration

### Repository Settings

1. Navigate to **Settings → Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `gh-pages` / root folder
4. **Enforce HTTPS**: ✅ (enabled)

### Important: Base Path Configuration

Since the portfolio is deployed to a **project repository** (not a user/org site), it's served from:

```
https://username.github.io/repository-name/
```

The `vite.config.ts` must reflect this:

```typescript
export default defineConfig({
  base: '/Gowtham-Portfolio/',  // ← Project-level base path
  // ...
})
```

**Note**: If you change the repository name, update the `base` path in `vite.config.ts` accordingly.

## Deployment Workflow (`.github/workflows/deploy.yml`)

### Trigger Events
- **On push to `main` branch**
- Automatically builds and deploys

### Workflow Steps

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'
      - run: npm install
      - run: npm run build
      - uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

### What It Does

1. **Checkout code** from the latest commit on `main`
2. **Setup Node.js 20** runtime
3. **Install dependencies** via npm
4. **Build production bundle** using Vite
5. **Deploy `dist/` folder** to `gh-pages` branch
6. GitHub Pages serves the `gh-pages` branch content

## Manual Deployment (Local)

If needed, you can deploy manually:

```bash
# Build the project
npm run build

# Push the dist/ folder to gh-pages branch
# Using gh-pages package (recommended)
npm install --save-dev gh-pages
npm run deploy  # (if script is configured in package.json)

# Or manually:
git add dist/
git commit -m "Deploy to GitHub Pages"
git push origin main
```

## Troubleshooting

### ❌ Site Not Deploying

1. **Check workflow status**
   - Go to repository **Actions** tab
   - Verify the deploy workflow succeeded

2. **Verify base path**
   - Confirm `vite.config.ts` has `base: '/Gowtham-Portfolio/'`
   - For user sites, use `base: '/'`

3. **Clear browser cache**
   - Hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)

### ❌ 404 Errors on Subpages

- Ensure all routing uses relative paths
- React Router should be configured with the base path

### ❌ Assets Not Loading

- Check browser DevTools → Network tab
- Verify asset URLs include the `/Gowtham-Portfolio/` prefix
- Update imports in components if needed

## Environment Variables

No environment variables are currently required for deployment. If you add them:

1. Create a `.env.local` file locally (ignored by git)
2. For GitHub Actions, add **Secrets** in **Settings**:
   - Go to **Settings → Secrets and variables → Actions**
   - Click **New repository secret**
   - Reference in workflow: `${{ secrets.YOUR_SECRET_NAME }}`

## Custom Domain (Optional)

To deploy to a custom domain:

1. **Add CNAME record** at your DNS provider pointing to `tekigowtham2204.github.io`
2. **Update GitHub Pages settings**
   - Settings → Pages → Custom domain
   - Enter your domain (e.g., `gowthalportfolio.com`)
3. **Redeploy** via push to `main`

## Monitoring Deployments

### GitHub Actions

- **Repository → Actions tab** shows build logs
- Green ✅ = successful deployment
- Red ❌ = build failed (check logs)

### GitHub Pages

- **Settings → Pages** shows deployment status
- **Published at** shows your live URL

## Security

- GitHub token automatically rotated per workflow run
- No sensitive data in repository
- HTTPS enforced by default

## Performance

- CDN-delivered from GitHub's edge servers
- Globally distributed
- Fast static asset delivery
- Zero cold start after first deployment

## Rollback / Revert

If a deployment breaks:

```bash
# Revert to previous commit
git revert HEAD
git push origin main

# GitHub Actions auto-redeploys the previous version
```

## Next Steps

✅ **Live Portfolio**: https://tekigowtham2204.github.io/Gowtham-Portfolio/

- Share the link with recruiters/hiring managers
- Add to LinkedIn, resume, Twitter/X bio
- Monitor GitHub Actions for deployment updates

---

**Deployment Status**: ✅ **Production Ready**

Last Updated: March 2026
