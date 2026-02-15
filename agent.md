# Agent Consistency Guide: Nevo24

This guide ensures that any AI agent working on the Nevo24 project maintains the **"Elegant & Refined"** aesthetic and adheres to the established coding standards.

## 1. Design Principles
- **Compact & High-Density**: Prefer smaller padding (`3.5rem` sections) and scaled-down typography for a professional desktop feel.
- **Subtle Depth**: Use the provided "Atmosphere Shadows" rather than borders where possible.
- **Logo Integrity**: ALWAYS use `height: 32px` for the brand logo with `image-rendering: crisp-edges`.
- **Refined Motion**: All transitions should use the custom cubic-bezier: `cubic-bezier(0.16, 1, 0.3, 1)`.
- **Glassmorphism**: Use `backdrop-filter: blur(12px)` for floating elements like the navbar.

## 2. Core Design Tokens (CSS Variables)
Always use these variables from `variables.css`:

| Category | Variable | Value / Usage |
| :--- | :--- | :--- |
| **Colors** | `--primary-color` | `#0f172a` (Deep Navy) |
| | `--accent-color` | `#2563eb` (Refined Blue) |
| | `--bg-light` | `#f1f5f9` (Light gray background) |
| **Typography**| `--font-family` | `'Inter', sans-serif` |
| | `h1` | `2.8rem`, line-height `1.1` |
| | `h2` | `1.85rem`, line-height `1.25` |
| **Spacing** | `--section-spacing`| `3.5rem` |
| **Shaping** | `--radius-lg` | `20px` (Default for cards) |

## 3. Component Library
Reuse existing classes instead of creating new ones:

### Logo
- Use `<img src="img/logo.png" height="32">` with `.logo` class wrapper for consistency.

### Buttons
- `.btn-cta`: Primary action button with shadow and lift effect.
- `.btn-outline`: Secondary action with accent border.
- `.btn-primary`: Standard blue button (used for forms/nav).

### Cards
- `.card`: Compact container with `1.5rem` padding and lift-on-hover effect.
- `.card-icon`: Scaled down icon container (`1.75rem`).

### Navigation
- `.logo`: Bolded primary color, -0.5px letter spacing.
- `.nav-link`: Underline-on-hover animation with accent color.

## 4. Coding Standards
- **Semantic HTML**: Use `<section>`, `<article>`, `<header>`, and `<footer>` appropriately.
- **Modular CSS**: Add new styles to `components/` if they are reusable, or `layouts/` for structural changes.
- **SEO**: Every page MUST have a unique `<title>` and `<meta name="description">`.
- **Accessibility**: Ensure all images have `alt` text and contrast remains high.
