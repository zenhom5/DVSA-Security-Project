# Bonus 5: Mass Assignment

## Summary
This bonus demonstrates a Mass Assignment vulnerability in the DVSA application. The backend accepts and processes all user-supplied fields without restriction, allowing attackers to modify sensitive attributes.

## Vulnerability
- **Type:** Mass Assignment  
- **Severity:** High  
- **Component:** API Gateway + Lambda  

## Root Cause
The application directly maps user input to backend objects without filtering or restricting allowed fields.

This allows attackers to inject additional parameters that should not be modifiable.

## Exploit Overview
An attacker includes extra fields (e.g., `role`, `isAdmin`) in the request.  
The backend processes these fields, resulting in privilege escalation or unintended behavior.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Unauthorized modification of sensitive fields  
- Privilege escalation  
- Manipulation of application behavior  

## Fix
- Implement allowlist validation for input fields  
- Ignore unexpected parameters  
- Enforce strict schema validation  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, additional fields are ignored and cannot influence the system.

## Screenshots
See `screenshots/` for:
- normal request  
- injected fields  
- exploit success  
- fix implementation  
- post-fix behavior  
