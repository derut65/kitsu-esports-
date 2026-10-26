# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

---

## Reporting a Vulnerability

The KITSU Esports team takes the security of its web assets, players, and community seriously. If you discover a security vulnerability, please report it responsibly.

### How to report:
- **Email**: [kitsuesports@gmail.com](mailto:kitsuesports@gmail.com)
- **Subject**: `[SECURITY VULNERABILITY] KITSU Esports Web`
- **Telegram (Admin)**: [@kitsuadmin](https://t.me/kitsuadmin)

Please include the following details in your report:
1. **Description**: Clear description of the vulnerability and potential impact.
2. **Steps to Reproduce**: Detailed reproduction steps or proof-of-concept (PoC).
3. **Environment**: Browser version, operating system, and any relevant network conditions.

### Response Timeline:
- **Initial acknowledgment**: Within 48 hours.
- **Triage & Assessment**: Within 5 business days.
- **Resolution & Deployment**: As quickly as possible depending on severity.

Please do not disclose the vulnerability publicly until it has been investigated and addressed by our team.

---

## Implemented Security Measures

The KITSU Esports portal is built as a hardened, high-performance static application:

1. **Content Security Policy (CSP)**:
   - Restricts script execution to trusted inline scripts (`'unsafe-inline' 'self'`).
   - Prevents unauthorized external network requests (`connect-src 'self'`).
   - Restricts fonts and styles to official Google Fonts endpoints (`fonts.googleapis.com`, `fonts.gstatic.com`).
   - Disables plugin execution (`object-src 'none'`).
   - Disables base tag hijacking (`base-uri 'self'`).
   - Automatically upgrades any insecure requests to HTTPS (`upgrade-insecure-requests`).

2. **Clickjacking & Framing Defense**:
   - `X-Frame-Options: DENY` header and `frame-ancestors 'none'` in CSP.
   - Client-side frame-busting script that hides content if embedded in unauthorized iframes.

3. **MIME-Type & Sniffing Protection**:
   - `X-Content-Type-Options: nosniff` enabled.

4. **Referrer & Privacy Protection**:
   - `Referrer-Policy: strict-origin-when-cross-origin` to prevent leaking private path or origin data.
   - All external outgoing links enforce `rel="noopener noreferrer" target="_blank"` to protect against reverse tabnabbing and window hijacking.

5. **Permissions Policy**:
   - Restricts access to sensitive device APIs: camera, microphone, geolocation, payment, USB, accelerometer, gyroscope, and magnetometer.

6. **Input & DOM Sanitization**:
   - Client-side hash routing sanitizes `location.hash` against injection characters before DOM matching.
   - Language switching validates against an allowed whitelist (`'ru'`, `'en'`).
   - Canvas download filenames are sanitized to prevent directory traversal or malformed file extensions.
   - Memory leaks from blob generation are avoided via proactive `URL.revokeObjectURL`.

7. **Zero Third-Party Tracking**:
   - No third-party trackers, cookies, or intrusive analytics scripts.
