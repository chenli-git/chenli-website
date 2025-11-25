# Chen Li's Personal Website

A modern, interactive personal website built with MkDocs Material, featuring Apple-inspired design, custom animations, and interactive elements.

🌐 **Live Site**: [https://chenli-git.github.io/](https://chenli-git.github.io/)

## Features

- 🎨 **Apple-inspired gradient design** with smooth color transitions
- 🖱️ **Custom interactive cursor** with trailing effect (desktop only)
- 🌊 **Mouse-following gradient background** for immersive experience
- 📱 **Fully responsive** with mobile-optimized experience
- 🌓 **Dark/Light mode** toggle with theme-specific styling
- ✨ **Smooth animations** on page elements and navigation
- 🎯 **Fixed navigation tabs** that stay accessible while scrolling
- 📊 **Cloudflare Web Analytics** for privacy-friendly visitor tracking

## Project Structure

```
chenli-website/
├── docs/                          # Content directory
│   ├── index.md                   # Home page
│   ├── about.md                   # About page with experience & education
│   ├── projects.md                # Projects showcase
│   ├── publications.md            # Academic publications
│   ├── contact.md                 # Contact information
│   ├── assets/
│   │   └── images/
│   │       └── profile.jpeg       # Profile picture
│   ├── js/
│   │   ├── cloudflare.js          # Cloudflare integration
│   │   └── interactive-background.js  # Custom cursor & background effects
│   └── stylesheets/
│       └── extra.css              # Custom CSS styling
├── .github/
│   └── workflows/
│       └── deploy.yml             # GitHub Actions deployment workflow
├── mkdocs.yml                     # MkDocs configuration file
└── README.md                      # This file
```

## Technology Stack

- **[MkDocs](https://www.mkdocs.org/)**: Static site generator
- **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)**: Modern theme with extensive features
- **[Cloudflare Web Analytics](https://www.cloudflare.com/web-analytics/)**: Privacy-first analytics
- **Docker**: For local development and consistent builds
- **GitHub Actions**: Automated deployment to GitHub Pages
- **Custom JavaScript**: Interactive elements and animations
- **Custom CSS**: Apple-inspired styling and effects

## Getting Started

### Prerequisites

- Docker installed on your system
- Git for version control
- GitHub account for hosting

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/chenli-git/chenli-website.git
   cd chenli-website
   ```

2. **Run with Docker** (recommended)
   ```bash
   docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
   ```
   
   Visit `http://localhost:8000` to see your site

3. **Or install locally**
   ```bash
   pip install mkdocs-material
   mkdocs serve
   ```

### Customization Guide

#### 1. Update Personal Information

**Profile Picture:**
- Replace `docs/assets/images/profile.jpeg` with your photo
- Update the alt text in `docs/index.md` and `docs/about.md`

**Contact Information:**
- Edit `docs/contact.md` with your email, LinkedIn, and GitHub

**About Page:**
- Update `docs/about.md` with your experience, education, and skills

#### 2. Modify Site Configuration

Edit `mkdocs.yml`:

```yaml
site_name: Your Name - Your Title
site_url: "https://yourusername.github.io/your-repo/"
site_author: Your Name
site_description: Your description

# Update repository links
repo_name: yourusername/your-repo
repo_url: https://github.com/yourusername/your-repo

# Update social links
extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/yourusername
    - icon: fontawesome/brands/linkedin
      link: https://www.linkedin.com/in/yourprofile/
    - icon: fontawesome/solid/envelope
      link: mailto:your.email@example.com
```

#### 3. Customize Colors

Edit `docs/stylesheets/extra.css`:

```css
:root {
  --gradient-start: #007AFF;  /* Change to your primary color */
  --gradient-mid: #5856D6;    /* Change to your secondary color */
  --gradient-end: #AF52DE;    /* Change to your accent color */
}
```

#### 4. Add/Remove Pages

1. Create a new markdown file in `docs/` (e.g., `blog.md`)
2. Add it to navigation in `mkdocs.yml`:
   ```yaml
   nav:
     - Home: index.md
     - About: about.md
     - Blog: blog.md  # Add your new page
     - Projects: projects.md
     - Publications: publications.md
     - Contact: contact.md
   ```

## Deployment

### GitHub Pages Setup

1. **Create GitHub repository**
   ```bash
   git remote add origin https://github.com/yourusername/your-repo.git
   ```

2. **Enable GitHub Actions**
   - The `.github/workflows/deploy.yml` file is already configured
   - Push your code to trigger automatic deployment:
     ```bash
     git add .
     git commit -m "Initial commit"
     git push -u origin main
     ```

3. **Configure GitHub Pages**
   - Go to repository Settings > Pages
   - Source: Deploy from a branch
   - Branch: `gh-pages` / `/ (root)`
   - Save

4. **Your site will be live at:**
   `https://yourusername.github.io/your-repo/`

## Key Features Explained

### Custom Cursor (Desktop Only)
- Location: `docs/js/interactive-background.js`
- Creates a custom circular cursor with trailing effect
- Automatically disabled on mobile devices
- Expands when hovering over links

### Interactive Background
- Gradient orb follows mouse movement
- Smooth interpolation for fluid motion
- Different effects for light/dark mode
- Static gradient on mobile for performance

### Navigation Tabs
- Fixed at top with `navigation.tabs.sticky`
- Larger clickable areas for better UX
- Hidden sidebar to maximize content space
- No animations to prevent movement

### Cloudflare Web Analytics
- Privacy-friendly analytics without cookies
- Location: `docs/js/cloudflare.js`
- To add your own:
  1. Sign up at [Cloudflare Web Analytics](https://www.cloudflare.com/web-analytics/)
  2. Get your analytics token
  3. Update `docs/js/cloudflare.js` with your token
  4. The script is automatically loaded via `mkdocs.yml`

### Glassmorphism Effect
- Content container with backdrop blur
- Semi-transparent background
- Elevated design with subtle shadows

## Troubleshooting

**Issue: Tabs moving when scrolling**
- Solution: Navigation animations are disabled in CSS
- Ensure `navigation.tabs.sticky` is enabled in `mkdocs.yml`

**Issue: Custom cursor not visible**
- Solution: Check if you're on a mobile device (cursor disabled on touch screens)
- Verify `interactive-background.js` is loaded in `mkdocs.yml`

**Issue: Profile picture not showing**
- Solution: Check file path is correct: `assets/images/profile.jpeg`
- Ensure image is committed and pushed to repository

**Issue: Deployment failing**
- Solution: Check GitHub Actions logs in repository > Actions tab
- Verify `mkdocs.yml` syntax is correct
- Ensure all required files are committed

## Contributing

Feel free to fork this repository and customize it for your own use! If you create something cool, I'd love to see it.

## License

This project is open source and available for anyone to use as a template for their personal website.

## Acknowledgments

- Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
- Inspired by Apple's design language
- Icons from [Font Awesome](https://fontawesome.com/)

## Contact

Chen Li - [chenli970701@gmail.com](mailto:chenli970701@gmail.com)

GitHub: [@chenli-git](https://github.com/chenli-git)  
LinkedIn: [linkedin.com/in/chenli-unc-ncsu](https://www.linkedin.com/in/chenli-unc-ncsu/)
