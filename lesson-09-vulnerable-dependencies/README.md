# Lesson 9: Vulnerable Dependencies

## Summary
This lesson demonstrates a Vulnerable Dependencies issue in the DVSA application. The application uses outdated or insecure third-party libraries that may contain known vulnerabilities.

## Vulnerability
- **Type:** Vulnerable Dependencies  
- **Severity:** Medium  
- **Component:** Application Libraries  

## Root Cause
The application depends on outdated or insecure libraries that are known to have vulnerabilities.

These dependencies are not regularly updated or audited.

## Exploit Overview
An attacker identifies vulnerable libraries used by the application and leverages known weaknesses to compromise the system.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Increased attack surface  
- Potential exploitation of known vulnerabilities  
- System compromise  

## Fix
- Update dependencies to secure versions  
- Regularly audit libraries  
- Use dependency scanning tools  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After updating dependencies, known vulnerabilities are no longer present.

## Screenshots
See `screenshots/` for:
- dependency list  
- vulnerability scan  
- fix implementation  
- verification  
