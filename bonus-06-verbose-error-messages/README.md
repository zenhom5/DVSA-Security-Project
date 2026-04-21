# Bonus 6: Verbose Error Messages

## Summary
This bonus demonstrates a Verbose Error Messages vulnerability in the DVSA application. The backend returns detailed error messages that expose internal system information.

## Vulnerability
- **Type:** Sensitive Information Disclosure / Verbose Errors  
- **Severity:** Medium  
- **Component:** AWS Lambda  

## Root Cause
The application returns full error details (such as stack traces or internal messages) directly to the user instead of handling them securely.

## Exploit Overview
An attacker sends malformed or unexpected input to trigger an error.  
The system responds with detailed error information, revealing internal implementation details.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Exposure of internal system details  
- Increased attack surface  
- Information leakage  

## Fix
- Return generic error messages  
- Log detailed errors internally only  
- Implement proper error handling  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, error messages are generic and do not expose internal details.

## Screenshots
See `screenshots/` for:
- error trigger  
- verbose error output  
- fix implementation  
- post-fix response  
