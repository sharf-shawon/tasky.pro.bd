# Proposal: Theme Customization & Data Portability

Elevate the Tasky user experience with sophisticated themes, list-specific colors, and improved data transfer capabilities.

## Problem
- The UI is currently locked to a single dark theme.
- Lists lack visual distinction from one another.
- Data portability is limited to sharing individual lists via URL parameters.

## Proposed Solution
1. **Theming System**: Implement a multi-theme engine (Light, Dark, Cyberpunk, etc.) using CSS variables and data attributes.
2. **Plaintext Preferences**: Store UI-only settings (like theme) in plaintext `localStorage` to allow immediate application on page load, preventing "theme flash."
3. **List Personalization**: Allow users to assign custom or random colors to individual lists, stored within the encrypted list data.
4. **Enhanced Portability**:
    - **QR Codes**: Generate QR codes for quick individual list transfer (mobile-friendly).
    - **Full Backup**: Support exporting all lists as an encrypted blob or a decrypted JSON file.

## Scope
- Update CSS to be fully themeable.
- Add UI for theme selection and list color picking.
- Integrate a lightweight QR code generator.
- Implement account-wide export/import logic.

## Non-Goals
- Real-time cloud sync (staying local-first/encrypted).
- Account systems or servers.
