# Lesson 8: Logic Vulnerabilities

## Summary
This lesson demonstrates a Logic Vulnerability in the DVSA application. The application logic relies on user-controlled input to make critical decisions, allowing attackers to manipulate the workflow.

## Vulnerability
- **Type:** Logic Vulnerability  
- **Severity:** High  
- **Component:** API Gateway + Lambda  

## Root Cause
The application trusts user input to control business logic decisions without proper validation or backend verification.

This allows attackers to bypass intended workflows by manipulating request parameters.

## Exploit Overview
An attacker modifies request parameters (such as flags or values) to change application behavior.

The backend processes these values directly, leading to unintended outcomes.

## Reproduction Steps
See `commands.txt` for full steps.

## Impact
- Bypass of business logic  
- Unauthorized actions  
- Manipulation of application workflow  

## Fix
- Do not trust user-controlled input for critical decisions  
- Enforce logic checks on the backend  
- Validate all parameters before processing  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, manipulated requests no longer change application behavior.

## Screenshots
See `screenshots/` for:
- normal behavior  
- manipulated request  
- exploit success  
- fix implementation  
- post-fix behavior  
