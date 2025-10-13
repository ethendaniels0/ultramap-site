# ultramap Website

A minimal, Typora-inspired website for ultramap - simple, powerful whiteboarding software.

## Features

- Clean, minimal design inspired by typora.io
- Responsive layout
- Static site (HTML/CSS/JS)
- Google Analytics integration
- GitHub Pages ready

## File Structure

```
ultramap_site/
├── index.html          # Main homepage
├── docs.html           # Documentation page
├── styles.css          # All styles
├── README.md           # This file
├── spec.md            # Original specifications
└── questions.md       # Q&A for website development
```

## Setup Instructions

### 1. Google Analytics Setup

To enable Google Analytics tracking:

1. Go to [Google Analytics](https://analytics.google.com/)
2. Create a new property for ultramap.io
3. Get your Measurement ID (format: `G-XXXXXXXXXX`)
4. Replace `GA_MEASUREMENT_ID` in both `index.html` and `docs.html` with your actual ID

**Files to update:**
- `index.html` (line 9 and 13)
- `docs.html` (line 9 and 13)

Search for `GA_MEASUREMENT_ID` and replace with your actual Google Analytics ID.

### 2. GitHub Pages Deployment

#### Option A: Deploy from GitHub Repository

1. **Create a new GitHub repository:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: ultramap website"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/ultramap-site.git
   git push -u origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to Settings > Pages
   - Under "Source", select "Deploy from a branch"
   - Select the `main` branch and `/ (root)` folder
   - Click Save

3. **Your site will be live at:**
   `https://YOUR_USERNAME.github.io/ultramap-site/`

#### Option B: Custom Domain (ultramap.io)

If you want to use your custom domain `ultramap.io`:

1. **Create a CNAME file:**
   ```bash
   echo "ultramap.io" > CNAME
   git add CNAME
   git commit -m "Add CNAME for custom domain"
   git push
   ```

2. **Configure DNS settings** at your domain registrar:

   Add these DNS records:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153

   Type: A
   Name: @
   Value: 185.199.109.153

   Type: A
   Name: @
   Value: 185.199.110.153

   Type: A
   Name: @
   Value: 185.199.111.153

   Type: CNAME
   Name: www
   Value: YOUR_USERNAME.github.io
   ```

3. **Update GitHub Pages settings:**
   - Go to Settings > Pages
   - Under "Custom domain", enter `ultramap.io`
   - Check "Enforce HTTPS"

4. Wait for DNS propagation (can take up to 48 hours)

### 3. Quick Deploy Commands

```bash
# Initialize git repository
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: ultramap website"

# Add your GitHub remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/ultramap-site.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Customization

### Updating Content

- **Homepage:** Edit `index.html`
- **Documentation:** Edit `docs.html`
- **Styles:** Edit `styles.css`

### Adding Real Screenshots

Replace the placeholder SVG in `index.html` (lines 44-56) with actual screenshots:

```html
<div class="screenshot-section">
    <div class="container">
        <img src="images/screenshot.png" alt="ultramap screenshot" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
    </div>
</div>
```

Create an `images/` folder and add your screenshots there.

### Color Scheme

To adjust colors, edit the CSS variables in `styles.css` (lines 9-16):

```css
:root {
    --color-primary: #2c2c2c;
    --color-secondary: #6c6c6c;
    --color-border: #e0e0e0;
    --color-bg: #ffffff;
    --color-bg-alt: #fafafa;
    --color-accent: #000000;
}
```

## Payment Integration

The "Buy Now" buttons currently link to `#buy`. To integrate payment:

1. Set up a payment processor (Stripe, Gumroad, Paddle, etc.)
2. Update the `href` attributes in `index.html`:
   - Early Bird button (line 79)
   - Full Price button (line 95)
   - Nav "Buy Now" button (line 23)

Example with Gumroad:
```html
<a href="https://gumroad.com/l/ultramap" class="btn-primary btn-large">Get Early Access</a>
```

## Local Development

To preview locally, simply open `index.html` in your browser, or use a local server:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (with http-server)
npx http-server

# Then visit: http://localhost:8000
```

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Responsive design for mobile and tablet
- No JavaScript frameworks required

## License

All rights reserved. This website is for ultramap.

## Support

For questions or issues, contact: support@ultramap.io
