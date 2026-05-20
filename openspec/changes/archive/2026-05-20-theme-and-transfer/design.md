# Design: Theme Customization & Data Portability

## Architecture

### 1. Storage Split
We will move from a single `__lk_data` key to two distinct storage areas:

- `__lk_prefs` (Plaintext):
    - `theme`: String (e.g., "dark", "light", "cyberpunk").
    - `lastExport`: ISO Date.
- `__lk_data` (Encrypted - Current):
    - `lists`: Array of objects. Each list now includes a `color` field (hex string).

### 2. Theming Engine
We will refactor the CSS to use a "Functional Variable" layer.

```css
/* Base variables defined per theme */
[data-theme="dark"] {
  --bg: #0f0e0d;
  --accent: #d4843a;
  /* ... */
}

/* Components use these variables */
.list-card {
  background: var(--surface);
  --l-accent: var(--accent); /* Default list accent */
}

/* If a list has a custom color, it's applied via JS */
/* <div class="list-card" style="--l-accent: #ff0000"> */
```

### 3. Early Theme Loading
To prevent flickering, the theme is applied as the first script in the `<head>` or at the very start of the `BOOT` sequence.

```javascript
const Prefs = {
  key: '__lk_prefs',
  data: { theme: 'dark' },
  load() {
    const s = localStorage.getItem(this.key);
    if (s) this.data = JSON.parse(s);
    this.apply();
  },
  save() {
    localStorage.setItem(this.key, JSON.stringify(this.data));
    this.apply();
  },
  apply() {
    document.documentElement.setAttribute('data-theme', this.data.theme);
  }
};
```

### 4. Data Portability

#### QR Code Transfer (Individual List)
- Use `qrious` (lightweight, ~5KB) to generate QR codes in the Share Modal.
- The QR will contain the existing `?share=...` URL.

#### Full Account Export
- **Encrypted (.enc)**: Downloads the raw `__lk_data` string.
- **Decrypted (.json)**: Decrypts the data first, then downloads as formatted JSON.
- **Import**: Accepts either format. If `.enc`, it assumes it was encrypted with a compatible key or asks for the key. (Actually, since `deviceKey` is random, importing an `.enc` file from another device requires knowing the source `deviceKey`. This might be too complex. We'll stick to plaintext JSON for cross-device manual transfer, or rely on the password-protected Share URL logic).

## UI/UX Changes
- **Settings Modal**: New modal to manage global theme and full account export/import.
- **Color Picker**: Added to the List Action bar (small color dots or a grid).
- **Share Modal Update**: Include a "Show QR Code" toggle.

## Technical Risks
- **QR Size**: Large lists might produce unscannable QR codes. We will warn the user if the payload is too large.
- **CSS Complexity**: Moving from hardcoded variables to a theme system requires careful regression testing of all UI states.
