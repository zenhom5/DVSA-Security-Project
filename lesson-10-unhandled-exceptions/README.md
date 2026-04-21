# Lesson 10: Unhandled Exceptions

## Summary
This lesson demonstrates an Unhandled Exceptions vulnerability in the DVSA application. The backend does not properly handle runtime errors, leading to exposure of internal details through error messages.

## Vulnerability
- **Type:** Unhandled Exceptions  
- **Severity:** Medium  
- **Component:** AWS Lambda  

## Root Cause
The application does not use proper error handling mechanisms such as try-catch blocks.

As a result, runtime errors propagate and expose internal information such as stack traces or system details.

## Exploit Overview
An attacker sends malformed or unexpected input to trigger an error.  
The application returns detailed error messages, revealing internal implementation details.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Exposure of internal system details  
- Information leakage  
- Increased attack surface  

## Fix
- Implement proper error handling using try-catch  
- Return generic error messages  
- Log detailed errors internally only  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, errors are handled gracefully and no internal details are exposed.

## Screenshots
See `screenshots/` for:
- error trigger  
- exposed error details  
- fix implementation  
- post-fix response  
