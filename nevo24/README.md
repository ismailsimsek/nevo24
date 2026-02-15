# Nevo24

This project follows a scalable static website architecture.

# Infos

Website name is nevo24.de

## Folder Structure

- **assets/**: Static assets like images and fonts.
- **css/**: Styling architecture.
  - `base/`: Global styles (Reset, Variables).
  - `components/`: Styles for specific UI components (e.g. `navbar.css`, `card.css`).
  - `layouts/`: Styles for layout patterns (e.g. `grid.css`).
  - `main.css`: The entry point importing all other CSS files.
- **js/**: JavaScript logic.
  - `components/`: JS modules for UI components.
  - `utils/`: Helper functions.
  - `main.js`: Main entry point (ES Module).
- **pages/**: Additional HTML pages.
- **index.html**: Main entry point.

## Development

1. Open `index.html` in your browser.
2. **Note**: For ES Modules (`<script type="module">`) to work properly locally without CORS errors, you should use a local server.
   - Python: `python3 -m http.server`
   - Node: `npx serve`
   - VS Code: Live Server extension
