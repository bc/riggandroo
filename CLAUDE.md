# CLAUDE.md - AI Assistant Guide for Riggandroo

## Project Overview

**Riggandroo** is a professional property management and rental marketing website for **Rigg and Roo LLC**, a Denver-based real estate company specializing in pet-friendly residential properties. The company was formed September 24, 2023 (Colorado LLC #20231982953).

- **Website**: riggandroo.com
- **Hosting**: GitHub Pages with automated deployment
- **Type**: Static website (no build step required)

### Properties Managed

| Address | Type | Neighborhood |
|---------|------|--------------|
| 3706 N Jackson St, Denver, CO 80205 | 4 bed, 2.5 bath | Clayton |
| 3704 N Jackson St, Denver, CO 80205 | 4 bed, 2.5 bath | Clayton |
| 3702 N Jackson St, Denver, CO 80205 | 4 bed, 3.5 bath | Clayton |
| 2142 S Gilpin St, Denver, CO 80210 | Residential | University Park |

---

## Directory Structure

```
riggandroo/
├── .github/workflows/
│   └── static.yml           # GitHub Pages deployment workflow
├── assets/
│   ├── css/                 # Compiled stylesheets
│   │   ├── main.css         # Main compiled stylesheet
│   │   ├── noscript.css     # No-JavaScript fallback styles
│   │   └── fontawesome-all.min.css
│   ├── js/                  # JavaScript files
│   │   ├── main.js          # Menu toggle, form handling
│   │   ├── util.js          # jQuery utility extensions
│   │   ├── jquery.min.js
│   │   ├── browser.min.js
│   │   └── breakpoints.min.js
│   ├── sass/                # SCSS source files (compile locally)
│   │   ├── base/            # Foundation styles
│   │   ├── components/      # Reusable component styles
│   │   ├── layout/          # Page layout structure
│   │   ├── libs/            # Mixins, variables, utilities
│   │   └── main.scss        # SCSS entry point
│   ├── webfonts/            # Font Awesome font files
│   └── vcard.vcf            # Contact card file
├── images/                  # Property and promotional images
├── snaply_photography_and_floorplans_sep2023/  # Professional photo assets
│   ├── 3702-jackson-st-denver-co-80205/
│   ├── 3704-jackson-st-denver-co-80205/
│   └── 3706-jackson-st-denver-co-80205/
├── index.html               # Home page
├── nearby.html              # Clayton neighborhood guide
├── 662_nearby.html          # Castle Rock neighborhood guide
├── gilpin_nearby.html       # University Park neighborhood guide
├── onboarding.html          # Tenant onboarding documentation
├── elements.html            # Style guide/template demo
├── test.html                # Web component testing
├── CNAME                    # Custom domain configuration
└── README.md                # Project notes
```

---

## Technology Stack

### Frontend
- **HTML5** with semantic markup
- **CSS3** via SCSS preprocessing (pre-compiled)
- **JavaScript** + jQuery for interactivity
- **Template**: Phantom by HTML5 UP (CCA 3.0 license)

### External Services & APIs
- **Font Awesome 6**: Icons (CDN kit ID: e1e2d876c8)
- **Google Fonts**: Source Sans Pro typeface
- **Google Maps**: Location embeds and directions
- **Vimeo**: Property video tours
- **WalkScore**: Neighborhood walkability scores
- **Snaply Photography**: Professional property images

### Deployment
- **GitHub Pages** with automatic deployment on push to main
- **Custom Domain**: riggandroo.com (configured in CNAME)
- **No build step**: Static files served directly

---

## Key Files

### HTML Pages

| File | Purpose |
|------|---------|
| `index.html` | Home page with property showcase, video tour, navigation |
| `nearby.html` | Clayton neighborhood guide (restaurants, shops, directions) |
| `662_nearby.html` | Castle Rock neighborhood guide |
| `gilpin_nearby.html` | University Park/Gilpin neighborhood guide |
| `onboarding.html` | Tenant move-in guide (utilities, contacts, checklist) |
| `elements.html` | Style guide demonstrating all UI components |
| `test.html` | Web component prototypes (CardComponent, LeasedCardComponent) |

### JavaScript

| File | Purpose |
|------|---------|
| `assets/js/main.js` | Menu toggle, form auto-resize, navigation events |
| `assets/js/util.js` | jQuery extensions for navList, panel functionality |

### SCSS Architecture

Located in `assets/sass/`:
- `base/` - Reset, page defaults, typography
- `components/` - Buttons, forms, tiles, tables, etc.
- `layout/` - Header, footer, menu, wrapper
- `libs/` - Variables (`_vars.scss`), mixins, breakpoints

---

## Development Guidelines

### Working with HTML

1. **Follow existing structure**: All pages use wrapper/header/menu/main/footer pattern
2. **Responsive classes**: Use row/column grid system (e.g., `class="row gtr-uniform"`)
3. **Breakpoint classes**: Size variants like `col-4 col-12-small`

### SCSS Modifications

1. SCSS must be compiled locally before committing
2. Variables are defined in `assets/sass/libs/_vars.scss`
3. Breakpoints use mixin syntax: `@include breakpoint('<=small')`
4. Available breakpoints: xxsmall (≤360px), xsmall (361-480px), small (481-736px), medium (737-980px), large (981-1280px), xlarge (1281-1680px)

### Adding New Pages

1. Copy structure from existing page (e.g., `nearby.html`)
2. Maintain consistent header/navigation
3. Include all required CSS/JS links
4. Add navigation link in menu section of each page

### Adding Images

1. Place general images in `/images/`
2. Property-specific photos go in `/snaply_photography_and_floorplans_sep2023/{address}/`
3. Use web-optimized versions from `images-for-web-or-mls/` folders

### Web Components (Experimental)

The `test.html` file contains custom web components:
- `<custom-card>` - Generic property card
- `<leased-card>` - Card with grayscale overlay for leased properties

These use Shadow DOM and custom attributes for data binding.

---

## Deployment

### Automatic Deployment

Push to `main` branch triggers GitHub Actions workflow (`.github/workflows/static.yml`):
1. Checkout code
2. Upload entire repository as artifact
3. Deploy to GitHub Pages

### Manual Deployment

Workflow can also be triggered manually via GitHub Actions UI.

---

## Important Contacts

### Property Management
- **Company**: Acorn and Oak Property Management
- **Manager**: Phillip Austin
- **Email**: phillip@acorn-oak.com
- **Phone**: (936) 520-4048

### Owner Contact
- **SMS Link**: +1-720-772-9042

### Environmental Health
- **Contact**: Tanya
- **Phone**: 720-907-4886

---

## Conventions

### Code Style
- Use semantic HTML5 elements
- 4-space indentation in HTML
- 2-space indentation in SCSS
- jQuery for DOM manipulation
- Comment complex sections

### Naming
- CSS classes: lowercase with hyphens (e.g., `gtr-uniform`)
- IDs: lowercase single words (e.g., `#wrapper`, `#header`)
- Files: lowercase with underscores for spaces

### Git Practices
- Descriptive commit messages focused on changes
- No build artifacts in commits (CSS is pre-compiled)
- Large media files (MP4) tracked with Git LFS

---

## Common Tasks

### Adding a New Neighborhood Guide
1. Copy `nearby.html` or `gilpin_nearby.html` as template
2. Update title, header, and content
3. Add local restaurants, attractions, and directions
4. Include Google Maps embed for the area
5. Link from main navigation

### Updating Property Information
1. Edit relevant HTML file(s)
2. Update any embedded addresses or contact info
3. Update images if needed in `/images/`

### Modifying Styles
1. Edit SCSS files in `assets/sass/`
2. Compile SCSS to CSS (use your local SCSS compiler)
3. Commit both `.scss` source and compiled `main.css`

---

## External Links

- **Zillow Rental Manager**: https://www.zillow.com/rental-manager/properties
- **Colorado SOS Business**: https://www.sos.state.co.us/biz/BusinessEntityDetail.do?masterFileId=20231982953
- **Theme License**: Creative Commons Attribution 3.0 (HTML5 UP Phantom)

---

## Notes for AI Assistants

1. **This is a static site** - No build process, server, or database
2. **SCSS is pre-compiled** - Changes to `.scss` require local compilation
3. **GitHub Pages deployment** - Push to main deploys automatically
4. **Pet-friendly focus** - This is a key selling point of the properties
5. **Multi-property site** - Content covers multiple Denver addresses
6. **Active development** - Web components in `test.html` are experimental
7. **External dependencies** - Font Awesome, Google Maps, Vimeo require internet
