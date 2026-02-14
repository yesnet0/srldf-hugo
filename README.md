# Security Research Legal Defense Fund - Hugo Site

A static Hugo site for the Security Research Legal Defense Fund, migrated from Webflow.

## Quick Start

### Local Development

```bash
# Install Hugo (if not already installed)
brew install hugo

# Clone the repository
git clone https://github.com/YOUR-ORG/srldf-hugo.git
cd srldf-hugo

# Start local development server
hugo server

# View the site at http://localhost:1313
```

### Build for Production

```bash
hugo --gc --minify
```

The built site will be in the `public/` directory.

## Project Structure

```
srldf-hugo/
├── .github/workflows/     # GitHub Actions for auto-deploy
├── content/
│   ├── _index.md          # Homepage (layout-driven)
│   └── privacy-policy.md  # Privacy Policy page
├── data/
│   ├── board.yaml         # Board member data
│   ├── faq.yaml           # FAQ items
│   └── resources.yaml     # Resource documents
├── layouts/
│   ├── _default/
│   │   ├── baseof.html    # Base template
│   │   └── single.html    # Single page template
│   ├── index.html         # Homepage template
│   └── partials/
│       ├── nav.html       # Navigation
│       └── footer.html    # Footer
├── static/
│   ├── css/main.css       # Styles
│   ├── js/main.js         # JavaScript
│   ├── images/            # Images and SVGs
│   ├── docs/              # PDF documents
│   ├── favicon.png        # Favicon
│   └── apple-touch-icon.png
└── hugo.toml              # Hugo configuration
```

## Updating Content

### Board Members

Edit `data/board.yaml`:

```yaml
- name: "New Member"
  role: "Board Member"
  affiliation: "Organization Name"
  image: "/images/headshot-newmember.jpg"
```

Add the headshot image to `static/images/`.

### FAQ Items

Edit `data/faq.yaml`:

```yaml
- question: "Your question here?"
  answer: "Your answer here. HTML is supported."
```

### Resources/Documents

1. Add the PDF to `static/docs/`
2. Edit `data/resources.yaml`:

```yaml
- title: "Document Title - Date"
  url: "/docs/your-document.pdf"
```

### Contact Emails

Edit `hugo.toml`:

```toml
[params]
  donateEmail = "donate@srldf.org"
  contactEmail = "info@srldf.org"
  securityEmail = "security@srldf.org"
```

## Deployment

### GitHub Pages (Automatic)

Push to the `main` branch and GitHub Actions will automatically build and deploy.

### Custom Domain

1. Add a `CNAME` file to `static/` with your domain:
   ```
   securityresearchlegaldefensefund.org
   ```

2. Update `baseURL` in `hugo.toml`:
   ```toml
   baseURL = "https://securityresearchlegaldefensefund.org/"
   ```

3. Configure DNS to point to GitHub Pages.

## Analytics

Google Tag Manager is configured via `hugo.toml`:

```toml
[params]
  googleTagManagerID = "GTM-N62F2L2"
```

## License

Content © Security Research Legal Defense Fund. All rights reserved.
