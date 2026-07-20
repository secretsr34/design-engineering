# sabahrahman.com - Portfolio Source

The production front-end of [sabahrahman.com](https://www.sabahrahman.com): homepage, case studies, and the F1 page. Hand-written HTML and CSS, vanilla JavaScript for scroll reveals and interactions, no framework, no build step.

This is an extract of the public pages. The live site additionally has a password-gated research area (edge middleware on Vercel) that is intentionally not part of this repository, and the case study walkthrough videos are omitted here for size - they play on the live site.

## What to look at

- `index.html` - the homepage. Typography-first layout, a serif/sans/mono type system, and an IntersectionObserver-driven reveal pattern with graceful degradation.
- `work/` - case study pages for enterprise design and engineering work (Amazon, Mayhem by ForAllSecure, Decision Intelligence). Shared layout system, per-page content.
- `images/` - case study assets, organized per project.

## Performance posture

- No JavaScript frameworks, no CSS frameworks, no icon fonts.
- System font stack with two hosted display faces, loaded with preconnect.
- Every page is a single request plus its images.

## Run it

```
python3 -m http.server 8000
```

Internal links assume the site root, so serve from this folder rather than opening files directly.
