# Bonus 7: Unauthenticated Access to Feedback Upload Function

## Summary
This bonus demonstrates an Unauthenticated Access vulnerability where a feedback upload function is exposed without requiring authentication.

## Vulnerability
- **Type:** Missing Authentication / Broken Access Control  
- **Severity:** High  
- **Component:** API Gateway + Lambda  

## Root Cause
The feedback upload endpoint does not enforce authentication checks, allowing any user to access and use the functionality.

## Exploit Overview
An attacker sends a request to the feedback upload endpoint without providing any authentication token.  
The system accepts the request and processes it.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Unauthorized access to functionality  
- Potential misuse of upload feature  
- Injection of arbitrary content  

## Fix
- Enforce authentication on the endpoint  
- Validate authorization before processing requests  
- Restrict access to authenticated users only  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, unauthenticated requests are rejected.

## Screenshots
See `screenshots/` for:
- unauthenticated request  
- successful upload  
- fix implementation  
- post-fix rejection  
