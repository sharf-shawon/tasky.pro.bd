# Capability: Security & Encryption

Handles client-side encryption of all user data and secure sharing.

## User Stories

- As a user, I want my tasks to be stored securely so that no one else can read them.
- As a user, I want to be able to share a list securely with someone else using a password.

## Functional Requirements

- **Encryption at Rest**:
    - All data stored in `localStorage` must be encrypted.
    - Use AES-GCM (256-bit) for encryption.
    - Use PBKDF2 (SHA-256, 250,000 iterations) for key derivation from a device key.
- **Device Key Management**:
    - Generate a cryptographically secure random device key if one doesn't exist.
    - Store the device key in `localStorage` (this key is specific to the browser/device).
- **Secure Sharing**:
    - Generate shareable links that contain the encrypted list data in the URL.
    - Support optional password protection for shared links.
    - If a password is used, the data in the link is encrypted with that password using PBKDF2 and AES-GCM.
    - If no password is used, the data is Base64 encoded (obfuscated but not securely encrypted).

## Non-Functional Requirements

- **Privacy**: No user data should ever leave the client unencrypted (except for the sharing link which is explicitly shared by the user).
- **Integrity**: Use AES-GCM to ensure that data hasn't been tampered with.

## Implementation Details

- **Crypto Module**: A self-contained module using the Web Crypto API.
- **Storage Abstraction**: A `Store` module that wraps `localStorage` and automatically handles encryption/decryption during load/save.
