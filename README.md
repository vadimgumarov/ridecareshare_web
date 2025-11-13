# RideCareShare Website

**Share Rides. Share Stories. Support Causes.**

Pre-launch landing page for RideCareShare - the world's first donation-powered airport carpooling mobile app.

---

## Overview

RideCareShare is a community mobility initiative that matches travelers heading in the same direction after landing at airports. Instead of paying the driver, riders donate to a cause they believe in. This repository contains the pre-launch landing page.

**Live Site**: [Coming Soon]
- GitHub Pages: https://vadimgumarov.github.io/ridecareshare_web/
- Custom Domain: https://ridecareshare.com (pending DNS configuration)

---

## Features

- **Single-Page Design**: All content in one HTML file for maximum performance
- **Dark/Light Theme**: Toggle with localStorage persistence
- **Responsive**: Mobile-first design, works on all devices
- **Accessible**: Semantic HTML, ARIA labels, keyboard navigation
- **Fast Loading**: ~20KB file size, no external dependencies
- **Waitlist Form**: Collect early adopter signups (email integration pending)
- **Social Media Integration**: Links to Facebook, X, Instagram, YouTube

---

## Tech Stack

- **HTML5**: Semantic structure
- **CSS3**: Custom properties (variables), flexbox, grid
- **Vanilla JavaScript**: ES6+, no frameworks
- **GitHub Pages**: Hosting and deployment
- **No Build Process**: Static site, edit and push

---

## Project Structure

```
ridecareshare_web/
├── index.html              # Main landing page
├── CLAUDE.md               # Universal development framework
├── .claude_project         # Project-specific configuration
├── .gitignore              # Git ignore rules
├── README.md               # This file
└── docs/                   # Documentation
    ├── CONTINUATION.md     # Current state and next steps
    ├── PROGRESS.md         # Development progress log
    ├── ISSUES.md           # Problems and solutions
    ├── deployment/         # Deployment guides
    │   ├── github-pages.md
    │   └── domain-setup.md
    └── social-media/       # Social media strategy
        └── deployment-plan.md
```

---

## Quick Start

### View Locally

**Option 1**: Open directly in browser
```bash
open index.html
```

**Option 2**: Use local server
```bash
python3 -m http.server 8000
# Visit: http://localhost:8000
```

### Deploy to GitHub Pages

1. Push changes to main branch:
```bash
git add .
git commit -m "Update: description"
git push origin main
```

2. GitHub Pages automatically deploys (1-2 minutes)

See `docs/deployment/github-pages.md` for detailed setup instructions.

---

## Development Workflow

1. **Edit**: Make changes to `index.html`
2. **Test**: Open in browser, check responsive design
3. **Commit**: Use descriptive commit messages
4. **Push**: Auto-deploys to GitHub Pages

### Testing Checklist

- [ ] Test on Chrome, Firefox, Safari
- [ ] Test responsive design (mobile, tablet, desktop)
- [ ] Verify dark/light theme toggle works
- [ ] Check waitlist form captures data
- [ ] Validate HTML at https://validator.w3.org
- [ ] Run Lighthouse audit in Chrome DevTools
- [ ] Test keyboard navigation (Tab, Enter, Space)

---

## Custom Domain Setup

The site will be accessible at two domains:
- **Primary**: ridecareshare.com
- **Redirect**: ridesharetogether.com → ridecareshare.com

See `docs/deployment/domain-setup.md` for DNS configuration instructions.

---

## Social Media

Connect with RideCareShare:
- **Facebook**: [To be created]
- **X (Twitter)**: [To be created]
- **Instagram**: [To be created]
- **YouTube**: [To be created]

See `docs/social-media/deployment-plan.md` for strategy and content calendar.

---

## Contributing

This is a solo project by Vadim. The mobile app is developed in a separate repository.

---

## Roadmap

### Phase 1: Pre-Launch (Current)
- [x] Design and develop landing page
- [x] Set up GitHub repository
- [ ] Deploy to GitHub Pages
- [ ] Configure custom domains
- [ ] Create social media accounts
- [ ] Integrate email service for waitlist

### Phase 2: Launch Preparation
- [ ] Add logo and branding images
- [ ] Create 60-second explainer video
- [ ] Add charity partner logos
- [ ] Set up analytics (privacy-friendly)
- [ ] A/B test different messaging

### Phase 3: Post-Launch
- [ ] Update with app download links
- [ ] Add user testimonials
- [ ] Create blog section
- [ ] Add press/media mentions

---

## Documentation

- **CONTINUATION.md**: Current development state, next steps
- **PROGRESS.md**: Chronological development log
- **ISSUES.md**: Problems encountered and solutions
- **CLAUDE.md**: Universal development framework and best practices
- **.claude_project**: Project-specific configuration

---

## License

© 2025 RideCareShare, All Rights Reserved.

---

## Contact

**Founder**: Vadim
**Website**: https://ridecareshare.com
**Email**: [To be set up]

---

**Status**: Pre-launch landing page ready for deployment
**Last Updated**: 2025-11-12
