# Bonus 4: Unprotected Admin Orders Endpoint

## Summary
This bonus demonstrates a Broken Access Control vulnerability where an admin-only endpoint is exposed without proper authorization checks.

## Vulnerability
- **Type:** Broken Access Control  
- **Severity:** Critical  
- **Component:** API Gateway + Lambda  

## Root Cause
The application exposes an admin endpoint without verifying whether the requesting user has administrative privileges.

## Exploit Overview
An attacker sends a request to the admin endpoint.  
Since no authorization check is performed, the system returns sensitive admin-level data.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Exposure of admin-level data  
- Unauthorized access to privileged functionality  
- Potential system compromise  

## Fix
- Enforce role-based access control (RBAC)  
- Verify user roles before granting access  
- Restrict admin endpoints to authorized users only  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, unauthorized users are denied access to the admin endpoint.

## Screenshots
See `screenshots/` for:
- unauthorized access  
- admin data exposure  
- fix implementation  
- post-fix restriction  
