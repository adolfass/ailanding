# AI Landing Page Agent Guidelines

## Project Overview

This is a static HTML/CSS landing page project for an "AI-Инженер" course landing page. The project contains:
- Single HTML file (`index.html`) with all content
- CSS styles embedded in the HTML `<style>` tag
- Minimal JavaScript for interactive components (accordion, smooth scrolling)
- No JavaScript framework or build system
- No external dependencies (except Google Fonts)
- All content is in Russian language
- Modern, clean design using Inter font family

## Development Commands

### Build Process
This project requires no build process as it consists of static HTML/CSS files only.
To preview changes, simply open `index.html` in a web browser.
No compilation, transpilation, or bundling steps are required.

### Running Locally
```bash
# Open directly in default browser (macOS)
open index.html

# Or use a simple HTTP server
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Linting
No automated linting is configured for this project. For CSS/HTML verification:
- Use W3C HTML Validator: https://validator.w3.org/
- Use CSS Validator: https://jigsaw.w3.org/css-validator/
- Manual code review for common issues

### Testing
Manual verification should be performed by:
1. Opening HTML files in a browser (Chrome, Firefox, Safari, Edge)
2. Checking responsive behavior at various viewport sizes:
   - Mobile: 375px, 414px
   - Tablet: 768px, 1024px
   - Desktop: 1440px, 1920px
3. Verifying all links open correctly (external links in new tabs)
4. Testing accordion FAQ interaction
5. Testing smooth scrolling for anchor links
6. Verifying all images load (check for broken images)
7. Checking color contrast for accessibility (WCAG 2.1 AA minimum)

### Running a Single Test
Not applicable - no automated test framework exists. All testing is manual visual verification.

## Code Style Guidelines

### HTML Style
- Use semantic HTML5 elements: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- Use `<button>` for interactive elements, `<a>` for links
- Always include `alt` text for images
- Use `aria-expanded` and `aria-hidden` for accordion accessibility
- Use `target="_blank"` and `rel="noopener"` for external links
- Use `loading="lazy"` for below-fold images
- Include JSON-LD Schema.org structured data for SEO

### CSS Style
- CSS variables for all theme values (colors, spacing, shadows, radii)
- Mobile-first responsive design with breakpoints at 640px, 768px, 1024px, 1440px
- Use `clamp()` for fluid typography
- Use `rem` units for scalable spacing
- Group properties: position, display, box-model, typography, visual
- Use cubic-bezier easing for smooth transitions
- Avoid `!important` unless absolutely necessary
- Add focus-visible states for keyboard accessibility
- Support reduced-motion preference with `@media (prefers-reduced-motion: reduce)`

### CSS Variable Naming
```css
--bg-primary: #ffffff;
--bg-secondary: #f8fafc;
--text-primary: #1e293b;
--text-secondary: #64748b;
--accent: #6366f1;
--accent-hover: #4f46e5;
--accent-light: rgba(99, 102, 241, 0.1);
--accent-gradient: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
--shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.05);
--shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
--shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
--radius-sm: 8px;
--radius-md: 12px;
--radius-lg: 16px;
--radius-full: 9999px;
```

### Naming Conventions
| Type | Convention | Example |
|------|------------|---------|
| CSS classes | lowercase with hyphens | `.hero-section`, `.pricing-card` |
| CSS custom properties | lowercase with hyphens | `--accent-color`, `--shadow-lg` |
| JavaScript variables | camelCase | `accordionButtons`, `scrollTarget` |
| JavaScript functions | camelCase | `initAccordion()`, `handleSmoothScroll()` |
| File names | lowercase with hyphens | `index.html`, `styles.css` |

### JavaScript Guidelines
- Use `const` and `let` - no `var`
- Use arrow functions for callbacks
- Cache DOM references outside loops
- Use `hidden` attribute for toggling visibility (not `display: none`)
- Use `aria-expanded` for accordion state
- Use `scrollIntoView({ behavior: 'smooth' })` for smooth scrolling
- Respect `prefers-reduced-motion`

```javascript
// Good example
document.querySelectorAll('.faq-question').forEach(btn => {
    btn.addEventListener('click', () => {
        const answer = btn.nextElementSibling;
        const expanded = btn.getAttribute('aria-expanded') === 'true';
        btn.setAttribute('aria-expanded', !expanded);
        answer.hidden = expanded;
    });
});
```

## Accessibility Requirements
- Color contrast ratio minimum 4.5:1 for normal text
- Color contrast ratio minimum 3:1 for large text
- All interactive elements must be keyboard accessible
- Focus states must be visible (`outline` with offset)
- Use `aria-label` for icon-only buttons
- Use `aria-expanded` for accordion
- Include `alt` text for all images
- Use semantic headings hierarchy (h1 → h2 → h3)

## SEO Requirements
- Include JSON-LD Schema.org for Course type
- Use semantic HTML5 structure
- Include meta description
- Use proper heading hierarchy
- Ensure all links have descriptive text

## Performance Requirements
- Inline critical CSS in `<style>` tag
- Lazy load below-fold images with `loading="lazy"`
- Use WebP format for images when possible
- Keep total HTML file under 500KB
- Minimize external requests
- Use system fonts as fallback

## Project Structure
```
ai_landing/
├── index.html          # Main landing page (all content inline)
├── AGENTS.md           # This file - agent guidelines
├── .gitignore          # Git ignore file
└── assets/             # Directory for images (empty by default)
    ├── images/
    └── placeholders/
```

## Important Links
- Expert Contact: https://t.me/itforbisness
- Expert Resume: https://spb.hh.ru/resume/632885bfff00de70d90039ed1f354333647341
- Expert Website: https://romambo.ru/
- Expert GitHub: https://github.com/adolfass?tab=repositories

## Agent Instructions
When working on this project:
1. Read existing files to understand content and structure before making changes
2. Maintain consistency with existing code style and patterns
3. Ensure all content is properly formatted and accessible
4. Test changes in multiple browsers and viewport sizes
5. Keep file organization consistent - don't create unnecessary nesting
6. Ensure all external links work and open in new tabs
7. Maintain semantic HTML structure for accessibility and SEO
8. Preserve CSS variable usage - don't introduce conflicting variables
9. Pay special attention to responsive design - test mobile to desktop
10. Keep accessibility in mind - color contrast, focus states, keyboard nav