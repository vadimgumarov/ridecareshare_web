# GitHub Pages Deployment Guide

## Quick Setup

### 1. Push Code to GitHub
```bash
# From project root directory
git add .
git commit -m "Initial commit: RideCareShare landing page"
git push origin main
```

### 2. Enable GitHub Pages
1. Go to repository: https://github.com/vadimgumarov/ridecareshare_web
2. Click **Settings** tab
3. Scroll to **Pages** section in left sidebar
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

### 3. Wait for Deployment
- GitHub will automatically deploy your site
- Usually takes 1-3 minutes for first deployment
- Check deployment status in **Actions** tab

### 4. Access Your Site
Your site will be available at:
```
https://vadimgumarov.github.io/ridecareshare_web/
```

---

## Custom Domain Setup (Optional)

Once GitHub Pages is live, you can configure custom domains.

### 1. Add Custom Domain in GitHub
1. In **Pages** settings, under **Custom domain**
2. Enter: `ridecareshare.com`
3. Click **Save**
4. Wait for DNS check to complete

### 2. Configure DNS Records
See `domain-setup.md` for detailed DNS configuration instructions.

---

## Automatic Deployments

Every push to the `main` branch will automatically trigger a new deployment:

```bash
# Make changes to index.html
git add index.html
git commit -m "Update: description"
git push origin main

# GitHub Pages will automatically redeploy (usually within 1-2 minutes)
```

---

## Troubleshooting

### Site Not Loading
- Check **Actions** tab for deployment status
- Ensure branch is set to `main` in Pages settings
- Clear browser cache and try again

### 404 Error
- Ensure `index.html` is in the root directory (not in a subfolder)
- Check that repository is public (or you have GitHub Pro for private repos)

### Changes Not Showing
- Wait 2-3 minutes for deployment to complete
- Hard refresh browser (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)
- Check **Actions** tab to verify deployment succeeded

### Custom Domain Not Working
- Verify DNS records are correctly configured (see `domain-setup.md`)
- DNS propagation can take up to 24-48 hours
- Use https://dnschecker.org to verify DNS propagation

---

## Performance Optimization

GitHub Pages serves static files very quickly, but you can further optimize:

1. **Enable HTTPS** - Automatically enabled, ensure "Enforce HTTPS" is checked
2. **Minimize file size** - Keep index.html under 100KB
3. **Use inline CSS/JS** - Already implemented (no external files)
4. **Optimize images** - When adding images, use WebP format and compression

---

## Monitoring

### Check Deployment Status
```bash
# View recent deployments
# Go to: https://github.com/vadimgumarov/ridecareshare_web/deployments
```

### Analytics (Optional)
Consider adding privacy-friendly analytics:
- **Plausible** - Privacy-focused, GDPR compliant
- **Simple Analytics** - No cookies, EU-based
- **Fathom** - Simple, privacy-first

Avoid Google Analytics for better privacy and faster page loads.

---

## Maintenance

### Regular Updates
```bash
# Update content
git pull origin main
# Make changes to index.html
git add index.html
git commit -m "Update: [description]"
git push origin main
```

### Backup
GitHub is your backup! All code is version-controlled and safe.

---

**Last Updated**: 2025-11-12
**Status**: Ready for deployment
