# Bonus 3: Missing Rate Limiting on Authentication

## Summary
This bonus demonstrates a Missing Rate Limiting vulnerability on the authentication endpoint. The system allows unlimited login attempts without restriction.

## Vulnerability
- **Type:** Missing Rate Limiting / Brute Force Risk  
- **Severity:** High  
- **Component:** Authentication Endpoint  

## Root Cause
The application does not implement rate limiting or throttling on authentication requests, allowing repeated attempts without restriction.

## Exploit Overview
An attacker sends multiple authentication requests in a short period of time.  
Since no limits are enforced, the attacker can attempt many credential combinations.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Increased risk of brute-force attacks  
- Account compromise  
- Resource abuse  

## Fix
- Implement rate limiting  
- Add request throttling  
- Introduce temporary lockouts after multiple failed attempts  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, repeated requests are limited or blocked.

## Screenshots
See `screenshots/` for:
- multiple login attempts  
- system behavior  
- fix implementation  
- post-fix rate limiting  
