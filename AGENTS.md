# AI Landing Page Agent Guidelines

## Project Overview
This is a static HTML/CSS landing page project for an "AI-Инженер" course landing page. The project contains:
- HTML content split across multiple text files (.txt)
- CSS styling files (.css)
- Minimal JavaScript for interactive components (accordion, smooth scrolling)
- No JavaScript framework or build system
- No external dependencies
- All content is in Russian language
- Modern, clean design using Inter font family

The landing page follows a modular approach where different sections (hero, features, pricing, testimonials, etc.) are stored in separate text files that need to be assembled into complete HTML pages.

## Development Commands

### Build Process
This project requires no build process as it consists of static HTML/CSS files only.
To preview changes, simply open the assembled HTML file in a web browser.
No compilation, transpilation, or bundling steps are required.

### Linting
No automated linting is configured for this project. For CSS files, follow standard CSS formatting guidelines:
- Use consistent 2-space indentation
- Group related properties (positioning, box model, typography, etc.)
- End each declaration with a semicolon
- Include a space after colon in property declarations
- Use lowercase for property names and values (except for font names and URLs)
- Keep selectors on separate lines for complex rules
- Add a blank line between rule sets for readability

### Testing
No automated testing framework is configured. Manual verification should be performed by:
1. Opening HTML files in a browser (Chrome, Firefox, Safari, Edge)
2. Checking responsive behavior at various viewport sizes (mobile, tablet, desktop)
3. Verifying all links and interactions work correctly
4. Ensuring proper color contrast for accessibility
5. Validating HTML structure using browser developer tools
6. Testing form interactions if any are present
7. Checking that images load correctly and have appropriate alt text

### Running a Single Test
Not applicable - no test framework exists. All testing is manual visual verification.

## Code Style Guidelines

### HTML/Text Files
- Use UTF-8 encoding
- Indent with 2 spaces
- Use lowercase for tag names and attributes
- Close all tags properly
- Use semantic HTML5 elements when appropriate
- Include alt text for all images
- Ensure proper heading hierarchy (h1-h6)
- Avoid inline styles; use CSS classes instead
- Use comments to delineate sections in large content files
- Ensure all special characters are properly escaped for HTML context
- Use meaningful, descriptive filenames that indicate content purpose
- When embedding SVG icons, ensure they have proper accessibility attributes
- Use boolean attributes correctly (e.g., `disabled`, `required`) without values
- Prefer native HTML elements over custom elements where appropriate
- Ensure form elements have associated labels for accessibility

### CSS Files
- Use 2-space indentation
- Group related properties together (positioning, box model, typography, etc.)
- End each declaration with a semicolon
- Include a space after colon in property declarations
- Use lowercase for property names and values (except for font names and URLs)
- Keep selectors on separate lines for complex rules
- Add a blank line between rule sets for readability
- Use meaningful class and ID names in lowercase with hyphens as separators
- Comment sections for major components
- Use CSS custom properties (variables) for theme values
- Mobile-first approach for responsive design
- Avoid !important unless absolutely necessary
- Use shorthand properties where appropriate (margin, padding, border, etc.)
- Organize properties alphabetically within each group for consistency
- Use rem units for scalable typography and spacing
- Use percentage or viewport units for fluid layouts
- Ensure sufficient color contrast ratios for accessibility
- Use CSS variables for consistent theming and easy updates
- Implement CSS resets or normalize.css principles for cross-browser consistency

### TypeScript/JavaScript Guidelines (if applicable)
- Although no JS framework is present, if adding custom JS:
  - Use ES6+ syntax (const/let, arrow functions, destructuring)
  - Follow Airbnb or StandardJS style guides
  - Use descriptive variable and function names
  - Comment complex logic
  - Ensure graceful degradation for older browsers
  - Use event delegation for dynamic content
  - Avoid global variables; use IIFE or modules if needed
  - Handle errors gracefully with try/catch where appropriate
  - Ensure all DOM manipulation waits for DOMContentLoaded
  - For DOM manipulation:
    - Cache DOM references when elements are accessed repeatedly
    - Use document.querySelectorAll() and NodeLists efficiently
    - Minimize reflows by batching DOM changes
    - Use documentFragment for multiple element insertions
    - Prefer textContent over innerHTML when inserting text to prevent XSS
    - Use modern DOM methods like append(), prepend(), before(), after(), remove() when possible
    - Use insertAdjacentHTML for precise HTML insertion when needed
    - Use cloneNode() for duplicating elements
    - Use classList API for class management (add, remove, toggle, contains)
    - Use dataset API for data attributes
    - Use textContent instead of innerHTML for text insertion to prevent XSS
  - For accordion implementations:
    - Use aria-expanded attribute for accessibility
    - Manage hidden property for visibility control
    - Animate using max-height transitions when needed
    - Ensure keyboard accessibility (Enter/Space keys)
  - For smooth scrolling:
    - Use element.scrollIntoView() with {behavior: 'smooth'} option
    - Prevent default anchor behavior with e.preventDefault()
    - Consider closing mobile menus after scroll if applicable
    - Respect user's prefers-reduced-motion media query

### Naming Conventions
- Files: lowercase with underscores as separators (e.g., `home_page_content.txt`)
- CSS classes: lowercase with hyphens (e.g., `.primary-button`)
- IDs: lowercase with hyphens (e.g., `#main-navigation`)
- JavaScript variables: camelCase (e.g., `userProfile`)
- JavaScript functions: camelCase (e.g., `initializeSlider()`)
- JavaScript constants: UPPER_SNAKE_CASE (e.g., `MAX_ITEMS`)
- Comments: Clear, descriptive, and in English
- CSS custom properties: lowercase with hyphens (e.g., `--primary-color`)
- Data attributes: lowercase with hyphens (e.g., `data-course-id`)

### Import/Include Guidelines
- CSS files: Use @import for Google Fonts at the top of the main CSS file
- No other import mechanisms used in this static project
- If adding external resources, use HTTPS and include integrity attributes
- Prefer self-hosted assets over external CDNs for reliability
- Use defer attribute for external scripts when they don't block rendering
- Load non-essential resources asynchronously

### Error Handling
- Static site: No runtime error handling needed
- Ensure all file paths are correct when deploying
- Provide fallback fonts in CSS font-family declarations
- Use appropriate HTTP status codes if served via web server
- Implement custom 404 and 500 error pages if hosted on a server
- Use meaningful alt text for images that conveys purpose
- Ensure form validation provides clear user feedback
- Use ARIA attributes to enhance accessibility of dynamic content
- Implement graceful degradation for CSS features not supported in older browsers

### Formatting
- Line length: Maximum 120 characters
- Trailing whitespace: Remove
- Character encoding: UTF-8
- End of file: Ensure newline at end of file
- Consistent quote usage (prefer single quotes for HTML attributes, double for CSS content)
- Use consistent spacing around operators and after commas
- Align vendor prefixes vertically when used
- Use empty lines to separate logical sections in long files
- Remove unused CSS rules and HTML comments before deployment
- Ensure consistent date formatting throughout content (DD.MM.YYYY format observed)

## Project Structure
- Text files (.txt): Contain HTML content sections for different parts of the landing page (hero, features, pricing, testimonials, etc.)
- CSS files (.css): Contain styling rules, including CSS variables for theming, responsive breakpoints, and component styles
- No JavaScript files present in the base project
- No build configuration files (no package.json, webpack.config, etc.)
- Assets (images, icons) would typically be referenced but may need to be added
- Content files follow naming convention indicating their purpose (e.g., hero_section.txt, pricing_cards.txt)

## Agent Instructions
When working on this project:
1. Read all existing files to understand the content and structure before making changes
2. Maintain consistency with existing code style - follow the established patterns in both HTML and CSS files
3. Ensure all content is properly formatted and accessible - test with screen readers and keyboard navigation
4. Test changes by viewing in multiple browsers/viewports (Chrome, Firefox, Safari, Edge) and at various screen sizes
5. Keep file organization consistent with existing patterns - don't create unnecessary nesting or deviate from established conventions
6. When creating new files, follow the naming convention seen in existing files (lowercase with underscores, descriptive names)
7. Ensure all content is properly escaped for HTML context to prevent XSS vulnerabilities
8. Maintain semantic HTML structure - use appropriate elements (header, nav, main, section, article, footer) for better accessibility and SEO
9. Preserve existing CSS variable usage and naming conventions - don't introduce conflicting variables or break the theming system
10. When modifying content, ensure it aligns with the course landing page purpose and maintains the professional tone
11. Pay special attention to responsive design - test how content adapts from mobile to desktop viewports
12. When working with text content files, maintain the modular approach - each file should contain a logical section of the page
13. Be mindful of file encoding - all files should be saved as UTF-8 to properly handle Russian characters
14. Validate any changes to CSS by checking that they don't break existing layouts or introduce visual regressions
15. Keep accessibility in mind when making changes - ensure sufficient color contrast, proper focus states, and logical tab order

## Cursor Rules
No Cursor rules found in this project.

## Copilot Instructions
No GitHub Copilot instructions found in this project.

## Additional Notes
- This is a static landing page - no server-side processing
- Content appears to be in Russian based on file examination
- Design follows a modern, clean aesthetic with Inter font family
- Price points and course packages are defined in the content files
- Testimonials section follows a specific format with avatar placeholders