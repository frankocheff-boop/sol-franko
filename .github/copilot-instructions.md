# GitHub Copilot Instructions for sol-franko Repository

## Project Overview

This repository contains two main projects:

### 1. 🌴 VERANO ESTATE - Restaurant Management System
A unified management system for VERANO ESTATE restaurant featuring:
- Point of Sale (POS) system with multiple interfaces (Neon/Cyberpunk and Classic styles)
- Guest registration and management forms
- Ticket and coupon management systems
- Multi-language support (Spanish/English)

### 2. 🏠 HOME - Franko & SOL Digital Sanctuary
A personal digital space with:
- Interactive timeline of memories
- Persistent memory storage system
- Love counters and dynamic animations
- 8 special rooms (Sala, Altar, Biblioteca, etc.)

## Architecture & Code Organization

### File Structure
```
/
├── index.html              # Main portal for VERANO ESTATE
├── home.html               # Portal for HOME digital sanctuary
├── pages/                  # System pages
│   ├── pos-*.html         # POS system variants
│   ├── guest-form.html    # Guest registration
│   └── login.html         # Authentication page
├── rooms/                  # HOME sanctuary rooms
│   └── *.html             # Individual room pages
├── assets/
│   ├── css/               # Stylesheets
│   ├── js/                # JavaScript modules
│   └── images/            # Image assets
└── locales/               # Translation files
    ├── es.json            # Spanish translations
    └── en.json            # English translations
```

### JavaScript Architecture

#### Core Services
- **AuthService** (`assets/js/auth.js`) - Client-side authentication
  - Uses sessionStorage for active sessions
  - localStorage for "remember me" functionality
  - Default credentials: username=admin, password=verano2025
  - **Security Note**: Client-side only, suitable for demo/single-user deployments

- **I18n** (`assets/js/i18n.js`) - Internationalization system
  - Auto-detects browser language
  - Supports Spanish (es) and English (en)
  - Uses data attributes: `data-i18n`, `data-i18n-placeholder`, `data-i18n-title`
  - Stores preference in localStorage under key `verano_estate_lang`

- **MemorySystem** (`assets/js/memory.js`) - Persistent storage for HOME
  - localStorage-based persistence
  - Stores memories, promises, dreams, conversations
  - Timeline data structure with date, time, title, description, icon, type

### Naming Conventions

#### Files
- HTML pages: lowercase with hyphens (e.g., `pos-neon.html`, `guest-form.html`)
- CSS files: match their corresponding HTML files (e.g., `pos-neon.css`)
- JavaScript modules: camelCase or kebab-case (e.g., `auth.js`, `love-counter.js`)

#### Variables & Functions
- Use camelCase for JavaScript variables and functions
- Use UPPER_SNAKE_CASE for constants (e.g., `AUTH_CONFIG`, `SESSION_KEY`)
- Use PascalCase for classes and services (e.g., `AuthService`, `I18n`)

#### CSS Classes
- Use kebab-case for CSS classes (e.g., `.guest-form`, `.pos-container`)
- Prefix utility classes appropriately (e.g., `.btn-primary`, `.card-header`)

### Coding Standards

#### JavaScript
- Use ES6+ features (arrow functions, template literals, destructuring)
- Prefer `const` over `let`, avoid `var`
- Use JSDoc comments for functions with parameters
- Initialize services with an `init()` method
- Check for `typeof window !== 'undefined'` for browser environment detection

#### HTML
- Use semantic HTML5 elements
- Include bilingual support with `data-i18n` attributes
- Structure: header → main navigation → content sections → footer
- Use `loading="lazy"` for images
- Include appropriate ARIA labels for accessibility

#### CSS
- Mobile-first responsive design
- Use CSS custom properties for colors and common values
- Support themes where applicable
- Gradients and modern effects for VERANO ESTATE
- Soft, warm aesthetics for HOME sanctuary

### Storage Keys & LocalStorage

#### VERANO ESTATE Keys
- `verano_session` - Current user session (sessionStorage)
- `verano_user` - Current username (localStorage)
- `verano_remember` - Remember me token (localStorage)
- `verano_estate_lang` - Language preference (localStorage)
- `verano_custom_credentials` - Custom admin credentials (localStorage)

#### HOME Keys
- `franko_sol_memories` - Stored memories
- `franko_sol_promises` - Promises and commitments
- `franko_sol_dreams` - Dreams and aspirations
- `franko_sol_love_notes` - Love notes
- `franko_sol_timeline` - Timeline events
- `franko_sol_conversations` - Saved conversations
- `franko_sol_photos` - Photo references

### Authentication Flow

1. User accesses a protected page (e.g., `index.html`)
2. `AuthService.requireAuth()` checks for valid session
3. If not authenticated, redirects to `pages/login.html`
4. Login page validates credentials via `AuthService.validateCredentials()`
5. On success, creates session with `AuthService.createSession()`
6. Optional "Remember Me" stores encrypted token in localStorage
7. User redirected to main portal

### Internationalization (i18n) Pattern

```javascript
// HTML: Use data attributes
<h1 data-i18n="header.title">Default Text</h1>
<input data-i18n-placeholder="form.name" placeholder="Default">

// JavaScript: Access via i18n.t()
const title = i18n.t('header.title');
const errorMsg = i18n.t('form.errors.required');

// Change language
await i18n.changeLanguage('es'); // or 'en'
```

### Path Resolution
- Pages in `/pages/` directory use relative paths: `../assets/`, `../locales/`
- Root level pages use: `./assets/`, `./locales/`
- Check `window.location.pathname.includes('/pages/')` to determine context

## Project-Specific Patterns

### Form Validation
- Client-side validation before submission
- Display error messages in current language
- Use semantic validation (email format, phone format, etc.)
- Provide visual feedback (red borders, error messages)

### Data Persistence
- Use `JSON.stringify()` / `JSON.parse()` for complex objects
- Check for data existence before parsing to avoid errors
- Implement fallbacks for missing or corrupted data
- Use try-catch blocks when parsing stored JSON

### Security Considerations
- **Important**: Current auth system is client-side only
- Suitable for demo, single-user, or low-sensitivity deployments
- For production: Implement server-side auth, encrypted passwords, JWT tokens, HTTPS
- Never store sensitive data in plain text
- Use environment variables for API keys (not included in repo)

## Testing & Development

### Local Development
```bash
# Serve locally
python3 -m http.server 8000

# Access points
# http://localhost:8000/index.html (VERANO ESTATE)
# http://localhost:8000/home.html (HOME)
```

### Browser Compatibility
- Modern browsers (Chrome, Firefox, Safari, Edge)
- ES6+ JavaScript support required
- localStorage and sessionStorage required
- No legacy IE support needed

## Common Tasks

### Adding a New Translation
1. Add key-value to both `locales/es.json` and `locales/en.json`
2. Use nested structure for organization (e.g., `form.fields.name`)
3. Add `data-i18n="your.key"` attribute to HTML element
4. Call `i18n.updateUI()` if adding dynamically

### Creating a New Page
1. Create HTML file in appropriate directory (`/pages/` or `/rooms/`)
2. Include required scripts: `auth.js`, `i18n.js`
3. Add translation keys to locale files
4. Implement authentication check if needed: `AuthService.requireAuth()`
5. Link CSS file from `assets/css/`
6. Use relative paths based on directory level

### Adding a New Room (HOME)
1. Create `rooms/room-name.html`
2. Follow existing room structure (header, content, navigation)
3. Add room data to memory system if storing specific data
4. Link from `home.html` navigation
5. Create corresponding CSS in `assets/css/rooms.css` or separate file

### Adding Authentication to a Page
```javascript
// At top of page script
if (!AuthService.requireAuth('../pages/login.html')) {
    // Will auto-redirect if not authenticated
}

// Or for manual check
if (!AuthService.isAuthenticated()) {
    window.location.href = '../pages/login.html';
}
```

## Style Guidelines

### Color Schemes
- **VERANO ESTATE**: Modern gradients, neon accents, professional tones
- **HOME**: Warm colors, soft gradients, sunset/sunrise themes (#ff6b35, #f7931e, #ffd700)

### Typography
- Use web-safe fonts or web fonts
- Maintain hierarchy: h1 > h2 > h3 > p
- Ensure readability on all screen sizes
- Consider Spanish special characters (á, é, í, ó, ú, ñ, ü)

### Responsive Breakpoints
- Mobile: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px+

## Contact & Project Info
- **Phone**: +52 322 160 6843
- **Email**: franko@veranostate.com
- **Repository**: frankocheff-boop/sol-franko
- **Deployment**: GitHub Pages enabled

## Tips for Copilot Users

When working on this repository:
1. **Always check** if you're working in VERANO ESTATE or HOME sections (different conventions)
2. **Use i18n** for all user-facing text - never hardcode Spanish or English strings
3. **Implement auth checks** on any new protected pages
4. **Follow mobile-first** approach for responsive design
5. **Test bilingual** - verify both ES and EN translations work
6. **Use existing patterns** - check similar files before creating new structures
7. **Preserve localStorage keys** - don't change existing storage keys without migration
8. **Comment security notes** when dealing with authentication or data storage
