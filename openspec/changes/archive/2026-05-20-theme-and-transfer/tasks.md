# Tasks: Theme Customization & Data Portability

## Phase 1: Theming Foundation
- [x] Refactor `:root` CSS variables into theme blocks (`[data-theme="..."]`).
- [x] Update all component CSS to use `--l-accent` (local accent) instead of `--accent`.
- [x] Implement `Prefs` module for plaintext storage of UI settings.
- [x] Update `BOOT` sequence to apply theme before rendering.

## Phase 2: Themes & List Colors
- [x] Create at least 3-4 initial themes (e.g., Dark, Light, Cyberpunk, Rose).
- [x] Implement a Theme Switcher UI in a new Settings modal.
- [x] Update `state.lists` and `renderLists` to support a per-list `color` field.
- [x] Add a simple color picker to the list card header.

## Phase 3: QR Sharing
- [x] Integrate `qrious` library (either via CDN or inlined if small enough).
- [x] Update Share Modal to display a QR code for the generated share link.
- [x] Add logic to check and warn if the share payload is too large for a QR code.

## Phase 4: Full Export/Import
- [x] Implement export functionality (JSON and Encrypted blob).
- [x] Implement import functionality in the Settings modal.
- [x] Final UI polish and regression testing.
