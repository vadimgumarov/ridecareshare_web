# Custom Domain Configuration Guide

## Overview

You own two domains:
- **ridecareshare.com** (Primary)
- **ridesharetogether.com** (Redirect to primary)

Both should point to your GitHub Pages site.

---

## Prerequisites

1. GitHub Pages must be enabled and working at: `https://vadimgumarov.github.io/ridecareshare_web/`
2. Access to domain registrar dashboard (where you purchased domains)

---

## Step 1: Configure Primary Domain (ridecareshare.com)

### A. Add CNAME File to Repository

Create a file named `CNAME` (no extension) in the root directory:

```bash
# Create CNAME file
echo "ridecareshare.com" > CNAME
git add CNAME
git commit -m "Add CNAME for custom domain"
git push origin main
```

### B. Configure GitHub Pages

1. Go to repository settings: https://github.com/vadimgumarov/ridecareshare_web/settings/pages
2. Under **Custom domain**, enter: `ridecareshare.com`
3. Click **Save**
4. Check **Enforce HTTPS** (wait for DNS to propagate first)

### C. Configure DNS Records at Domain Registrar

Log into your domain registrar and add these DNS records for **ridecareshare.com**:

#### For Apex Domain (ridecareshare.com)

**Option 1: A Records (Recommended)**
```
Type: A
Name: @
Value: 185.199.108.153
TTL: 3600

Type: A
Name: @
Value: 185.199.109.153
TTL: 3600

Type: A
Name: @
Value: 185.199.110.153
TTL: 3600

Type: A
Name: @
Value: 185.199.111.153
TTL: 3600
```

**Option 2: ALIAS Record (if supported by registrar)**
```
Type: ALIAS
Name: @
Value: vadimgumarov.github.io
TTL: 3600
```

#### For WWW Subdomain (www.ridecareshare.com)

```
Type: CNAME
Name: www
Value: vadimgumarov.github.io
TTL: 3600
```

---

## Step 2: Configure Secondary Domain (ridesharetogether.com)

### Option A: Domain Forwarding (Easiest)

Most registrars offer domain forwarding:

1. Log into domain registrar
2. Find "Domain Forwarding" or "URL Redirect" setting
3. Configure:
   - **From**: ridesharetogether.com
   - **To**: https://ridecareshare.com
   - **Type**: 301 Permanent Redirect
   - **Include Path**: Yes
   - **Forward www**: Yes

### Option B: DNS Records (Alternative)

If your registrar doesn't support forwarding, use the same DNS configuration as primary domain:

```
Type: A Records (same 4 IP addresses as above)
Type: CNAME for www → vadimgumarov.github.io
```

Then configure in GitHub Pages settings to accept both domains.

---

## Step 3: Verification

### DNS Propagation Check

DNS changes can take 24-48 hours to propagate globally. Check status:

```bash
# Check A records
dig ridecareshare.com

# Check CNAME records
dig www.ridecareshare.com

# Or use online tool
# https://dnschecker.org
```

### Test Domains

Once DNS propagates, test all variations:

```
http://ridecareshare.com
https://ridecareshare.com
http://www.ridecareshare.com
https://www.ridecareshare.com

http://ridesharetogether.com
https://ridesharetogether.com
```

All should redirect to: `https://ridecareshare.com`

---

## Step 4: Enable HTTPS

1. Wait for DNS to fully propagate (check with dnschecker.org)
2. Go to GitHub Pages settings
3. Check **Enforce HTTPS**
4. Wait a few minutes for SSL certificate to provision
5. Verify HTTPS works at: https://ridecareshare.com

---

## Common Domain Registrars

### GoDaddy
- DNS Management: https://dcc.godaddy.com/manage/
- Add/Edit DNS Records under "DNS Management"
- Domain Forwarding under "Forwarding"

### Namecheap
- Dashboard → Domain List → Manage
- Advanced DNS tab for DNS records
- Domain tab → Redirect Domain for forwarding

### Google Domains
- DNS settings in domain dashboard
- Use Custom records for A/CNAME
- Website section for forwarding

### Cloudflare
- DNS tab for records
- Page Rules for redirects (free tier allows 3 rules)

---

## Troubleshooting

### Domain Not Resolving
- Wait 24-48 hours for DNS propagation
- Use https://dnschecker.org to check global propagation
- Verify A records point to correct GitHub Pages IPs
- Clear browser DNS cache

### HTTPS Not Working
- Ensure DNS is fully propagated first
- GitHub needs valid DNS to provision SSL certificate
- Can take up to 24 hours after DNS propagation
- Check "Enforce HTTPS" is enabled in Pages settings

### WWW Not Working
- Verify CNAME record for www subdomain
- Ensure CNAME points to vadimgumarov.github.io (not ridecareshare.com)
- Check DNS propagation for www subdomain specifically

### Secondary Domain Not Redirecting
- Verify forwarding is configured as 301 Permanent
- Ensure "Include Path" is enabled
- Test without browser cache (incognito mode)

---

## DNS Record Reference

**GitHub Pages A Record IP Addresses** (as of 2025):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**Note**: These IPs rarely change, but verify current IPs at:
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

---

## Email Setup (Future)

If you want to receive emails at @ridecareshare.com:

1. Use Google Workspace, Zoho Mail, or ProtonMail
2. Add MX records provided by email service
3. Keep A/CNAME records for website unchanged
4. MX records handle email, A/CNAME handle web traffic

---

**Last Updated**: 2025-11-12
**Status**: Ready for DNS configuration
**Estimated Setup Time**: 5-10 minutes + 24-48 hours DNS propagation
