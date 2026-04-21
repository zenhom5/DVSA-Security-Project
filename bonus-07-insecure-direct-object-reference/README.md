# Bonus 7: Insecure Direct Object Reference (IDOR)

## Summary
This bonus demonstrates an Insecure Direct Object Reference (IDOR) vulnerability in the DVSA application. The system allows access to resources based solely on user-supplied identifiers without proper validation.

## Vulnerability
- **Type:** Insecure Direct Object Reference (IDOR)  
- **Severity:** High  
- **Component:** API Gateway + Lambda  

## Root Cause
The application uses direct object identifiers (such as order IDs) from user input without verifying ownership or authorization.

## Exploit Overview
An attacker modifies the object identifier (e.g., `order-id`) in the request.  
Since the backend does not validate ownership, it returns data belonging to another user.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Unauthorized data access  
- Exposure of sensitive information  
- Violation of data isolation  

## Fix
- Validate ownership of requested resources  
- Enforce authorization checks  
- Avoid direct trust of user-supplied identifiers  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, access to unauthorized resources is denied.

## Screenshots
See `screenshots/` for:
- normal access  
- modified identifier request  
- exploit success  
- fix implementation  
- post-fix denial  
