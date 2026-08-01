# Security Policy

## Scope

This repository contains educational HTML and CSS examples. Security reports should focus on repository-owned code, examples, configuration, or documentation that could create a realistic security or privacy risk.

## Reporting

Please do not publish sensitive details in a public issue. Report the affected file, the risk, reproduction steps, and a suggested mitigation through a private GitHub security report when available.

## Security Baseline

- Do not commit passwords, API keys, access tokens, private keys, personal records, or organization-confidential data.
- Do not place secrets in HTML, CSS, client-side JavaScript, comments, or example configuration because browser-delivered content is public.
- Use HTTPS for external resources when possible.
- Review third-party scripts, fonts, iframes, and CDN assets before adding them.
- Avoid inline event handlers and unsafe HTML injection in examples that include JavaScript.
- Use restrictive iframe attributes and explain trust boundaries when embedding external content.
- Use synthetic or anonymized data in demonstrations.
- Keep form examples educational; do not imply that client-side validation alone provides server-side security.

## Accessibility and User Safety

Security-quality review also includes clear focus states, keyboard access, readable contrast, meaningful labels, safe link behavior, and non-deceptive user interfaces.

## Supported Content

Security fixes are prioritized for the current lessons, examples, and main branch. Historical examples may be retained for learning but should be clearly identified when they demonstrate outdated practices.
