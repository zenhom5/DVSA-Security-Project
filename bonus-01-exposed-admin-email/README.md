# Bonus 1: Exposed Admin Email

## Summary
This bonus demonstrates a Sensitive Information Disclosure issue where an administrator email address is exposed through the application responses or configuration.

## Vulnerability
- **Type:** Sensitive Information Disclosure  
- **Severity:** Medium  
- **Component:** API / Configuration  

## Root Cause
The application exposes internal or sensitive information, such as the admin email, without proper restriction.

This occurs due to improper filtering of response data or insecure configuration.

## Exploit Overview
An attacker performs normal application requests and observes that the response includes an administrator email address.

This information can be used for targeted attacks such as phishing or user enumeration.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Exposure of sensitive internal information  
- Increased risk of targeted attacks  
- Information leakage  

## Fix
- Remove sensitive data from responses  
- Avoid exposing internal identifiers  
- Implement proper response filtering  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, the administrator email is no longer exposed in any response.

## Screenshots
See `screenshots/` for:
- exposed email  
- fix implementation  
- post-fix verification  
