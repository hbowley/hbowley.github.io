# Hannah's Professional Portfolio

A clean, minimal portfolio website built with Hugo. Showcasing data science projects, experience, and resume.

## ✨ Features

- **Clean & Minimal Design** — Fast-loading, responsive, data-science aesthetic
- **Projects Gallery** — Linked directly to your GitHub repositories
- **Resume** — Embedded PDF + formatted content
- **Dark Header, Light Body** — Professional look
- **Mobile Responsive** — Works great on all devices
- **Fast** — Static HTML, no JavaScript bloat

## 📋 Structure

```
portfolio/
├── content/
│   ├── projects/        # Individual project pages
│   └── resume.md        # Resume content
├── themes/minimal/      # Custom theme
│   ├── layouts/         # HTML templates
│   └── static/css/      # Styling
├── static/              # Files served as-is (resume.pdf, etc.)
└── hugo.yaml            # Site configuration
```

## 🚀 Deployment to GitHub Pages

### Initial Setup

1. **Create a new repository** on GitHub:
   - Name it `hbowley.github.io` (replace with your GitHub username)
   - Make it public
   - Add a `.gitignore` to ignore the `public/` folder (GitHub Actions will handle deployment)

2. **Push this site to GitHub**:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio commit"
   git remote add origin https://github.com/hbowley/hbowley.github.io.git
   git branch -m main
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to your repo Settings → Pages
   - Under "Build and deployment", select "GitHub Actions"
   - The workflow will automatically deploy on every push to `main`

### Local Development

```bash
# Install Hugo (if you haven't already)
# macOS: brew install hugo
# Linux: sudo apt-get install hugo
# Windows: choco install hugo-extended

# Serve locally
hugo server -D

# Visit http://localhost:1313
```

### Updating Content

- **Edit projects**: Add/edit `.md` files in `content/projects/`
- **Edit resume**: Edit `content/resume.md`
- **Update PDF**: Replace `static/resume.pdf` with your latest resume
- **Edit homepage**: Modify `themes/minimal/layouts/index.html`

Changes are automatically deployed to GitHub Pages when you push to `main`.

## 🎨 Customization

### Colors
Edit `themes/minimal/static/css/style.css` and change the CSS variables:
```css
:root {
    --primary: #1a1a1a;      /* Header background */
    --accent: #0066cc;       /* Link color */
    --text: #333333;         /* Text color */
    /* etc */
}
```

### Fonts
Update font families in `style.css`:
```css
html, body {
    font-family: /* your font stack */;
}
```

### Domain (Optional)
To use a custom domain like `hbowley.dev`:

1. Point your domain DNS to GitHub Pages:
   - Add CNAME record: `hbowley.github.io`
   - Or use GitHub's nameservers

2. Add a `CNAME` file to `static/`:
   ```
   hbowley.dev
   ```

3. Go to Repo Settings → Pages → Custom domain → Enter `hbowley.dev`

## 📝 Adding Projects

Create a new file in `content/projects/`:

```markdown
---
title: "Project Title"
date: 2024-02-17
link: "https://github.com/hbowley/project-name"
---

Brief description of the project.

**Tech:** R, Python, Shiny, etc.
```

Save and push to GitHub — it automatically appears on the site!

## 🔗 Update Links

In `hugo.yaml`, update the contact link if needed:
```yaml
menu:
  main:
    - name: "Contact"
      url: "mailto:your-email@example.com"
```

## 📊 Analytics (Optional)

To add Google Analytics, create `themes/minimal/layouts/partials/analytics.html` and include it in `baseof.html`:

```html
{{ if .Site.Params.googleAnalyticsID }}
<script async src="https://www.googletagmanager.com/gtag/js?id={{ .Site.Params.googleAnalyticsID }}"></script>
<script>
  // Your tracking code
</script>
{{ end }}
```

Then add to `hugo.yaml`:
```yaml
params:
  googleAnalyticsID: "G-XXXXXXXXXX"
```

## 🛠️ Troubleshooting

### Site not updating?
- Make sure you pushed to `main` branch
- Check `.github/workflows/hugo.yml` was included in the push
- Wait ~2 minutes for GitHub Actions to complete

### Local build failing?
- Run `hugo version` to check it's installed
- Try `hugo clean` then `hugo` to rebuild
- Check the error message for typos in markdown files

### Links broken?
- Make sure URLs in `hugo.yaml` and content files use relative paths
- Use `{{ relURL }}` in templates

## 📞 Contact & Support

For issues or questions, check:
- [Hugo Documentation](https://gohugo.io/documentation/)
- [GitHub Pages Help](https://docs.github.com/en/pages)
- [Theme Guide](themes/minimal/README.md)

---

Built with ❤️ and [Hugo](https://gohugo.io)
