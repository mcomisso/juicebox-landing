# JuiceBox Landing Page

Static landing page for JuiceBox iOS app, deployable to **getjuicebox.app**.

## Features

- 🎨 Modern, responsive design
- ⚡ Single-file HTML (no build process required)
- 📱 Mobile-optimized
- 🎯 Highlights key app features
- 🌈 Uses app's color scheme (#10b981 electric green)
- ♿ Accessible and SEO-friendly

## Publishing to GitHub Pages

### Option 1: Deploy from this folder

1. Create a new repository for the landing page (e.g., `juicebox-landing`)
2. Copy the contents of this `Landing` folder to the repository
3. Go to repository Settings → Pages
4. Set Source to "Deploy from a branch"
5. Select `main` branch and `/` (root) folder
6. Click Save
7. Your site will be published at `https://yourusername.github.io/juicebox-landing`

### Option 2: Use GitHub Actions (recommended for custom domain)

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./Landing
```

## Custom Domain Setup (getjuicebox.app)

1. In your repository, go to Settings → Pages
2. Under "Custom domain", enter: `getjuicebox.app`
3. Click Save (this creates a CNAME file)
4. In your domain registrar (where you bought getjuicebox.app):
   - Add an A record pointing to GitHub Pages IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Or add a CNAME record pointing to: `yourusername.github.io`

5. Wait for DNS propagation (can take up to 24 hours)
6. Enable "Enforce HTTPS" in GitHub Pages settings

## Local Preview

Simply open `index.html` in your web browser - no server required!

## Customization

### Update App Store Link

Replace the placeholder in `index.html`:

```html
<a href="#" class="btn btn-primary">
```

With your actual App Store URL:

```html
<a href="https://apps.apple.com/app/id..." class="btn btn-primary">
```

### Update GitHub Links

The GitHub repository link is currently set to:
- `https://github.com/matcom/BatteryLogger-iOS`

Update if your username is different.

### Add Screenshots

Consider adding device mockups with screenshots:
1. Use tools like [Rotato](https://rotato.app) or [Screely](https://screely.com)
2. Add images to a `Landing/images` folder
3. Insert into HTML between sections

### Color Scheme

Primary colors are set in CSS variables:
- Primary: `#10b981` (electric green)
- Success: `#10b981`
- Warning: `#f59e0b`
- Danger: `#ef4444`

## File Structure

```
Landing/
├── index.html          # Main landing page (self-contained)
└── README.md          # This file
```

## Technologies Used

- HTML5
- CSS3 (with CSS Variables)
- Responsive design (flexbox/grid)
- No JavaScript required
- No external dependencies

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

Same as JuiceBox app license.
