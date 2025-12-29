# CLAUDE.md - RIDECARESHARE_WEB

> Pre-launch Landing Page for RideCareShare Mobile App

> **Note:** Core rules (communication, code standards, error recovery, version control) are in global memory (`~/.claude/settings.json`). This file contains PROJECT-SPECIFIC configuration only.

---

## QUICK START

```
1. Read docs/CONTINUATION.md
2. Read .claude_project for detailed config
3. State: [branch: X | issue: #Y | status: Z]
4. Make changes, test in browser, commit
```

---

## PROJECT

| | |
|---|---|
| **What** | Static landing page for RideCareShare mobile app pre-launch |
| **Why** | Introduce concept, collect waitlist signups, professional first impression |
| **Who** | Potential users before mobile app launch |
| **Phase** | Pre-launch (1.0.0) |

### Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| Frontend | HTML/CSS/JS | Vanilla, no frameworks |
| Backend | None | Static site |
| Database | None | Waitlist via email service |
| Testing | Manual | Browser-based testing |
| Hosting | GitHub Pages | Auto-deploy from main |

### Links

| Resource | URL |
|----------|-----|
| Repository | GitHub |
| Production | https://ridecareshare.com |
| GitHub Pages | https://vadimgumarov.github.io/ridecareshare_web/ |

### Development Context

- **Approach:** Solo development
- **Tracking:** GitHub Issues
- **CI/CD:** GitHub Pages (auto-deploy on push to main)

---

## REFERENCES

| Resource | Location |
|----------|----------|
| Principles | `FOUNDATION/domains/it/PRINCIPLES-IT.md` |
| Procedures | `FOUNDATION/procedures/MANIFEST.md` |
| Project Config | `.claude_project` (detailed stack, architecture) |

---

## PROJECT DOCS

| Doc | Location | Purpose |
|-----|----------|---------|
| Continuation | `docs/CONTINUATION.md` | Current state |
| Progress | `docs/PROGRESS.md` | Accomplishment log |
| Issues | `docs/ISSUES.md` | Problems & solutions |
| Deployment | `docs/deployment/` | GitHub Pages, domain setup |

---

## PROJECT RULES

### Safety

- **NEVER** change brand name from RideCareShare
- **NEVER** add frameworks (React, Vue, etc.) — keep it static
- **NEVER** break responsive design — must work on all devices
- **NEVER** ignore accessibility — all users must be able to navigate
- Primary domain: ridecareshare.com (ridesharetogether.com redirects)
- Design pattern: muted earth tones, smooth transitions, accessible

### Testing (Manual Browser Testing)

| Test | How |
|------|-----|
| Cross-browser | Chrome, Firefox, Safari, Edge |
| Responsive | DevTools device toolbar (Cmd+Shift+M) |
| Accessibility | Lighthouse audit |
| Performance | Lighthouse score > 90 |
| JavaScript | Browser console (no errors) |

### Quality Gates (Pre-Commit)

- [ ] All sections render correctly
- [ ] Theme toggle works (light/dark)
- [ ] Responsive design passes (mobile/tablet/desktop)
- [ ] No JavaScript console errors
- [ ] No broken links

### Constraints

- Single index.html file (all-in-one)
- No build process or dependencies
- Privacy-first (no tracking scripts)
- Fast loading (< 2 seconds)

### Conventions

- Semantic HTML5
- CSS variables for theming
- Mobile-first responsive design

---

## COMMANDS

```bash
# Development
open index.html                    # Open in browser
python3 -m http.server 8000       # Local server

# Validation
# Browser DevTools (F12) for console/network
# Lighthouse for performance/accessibility
# https://validator.w3.org/ for HTML validation

# Deploy
git add . && git commit -m "message" && git push
# (auto-deploys to GitHub Pages)
```

---

## STATE TRACKING

Every code-related response starts with:

```
[branch: feature/123-feature-name | issue: #123 | status: clean]
```

---

**Template Version:** 5.0
**Template Type:** solo-soft (static variant)
**Last Updated:** 2025-12-28
**Inherits From:** `~/.claude/settings.json` (global memory)
**See Also:** `.claude_project` for detailed configuration
