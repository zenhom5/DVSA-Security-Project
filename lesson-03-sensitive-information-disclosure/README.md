# Lesson 3: Sensitive Information Disclosure

## Summary
This lesson demonstrates a Sensitive Information Disclosure vulnerability in the DVSA application. The backend exposes more data than necessary in API responses, allowing users to access sensitive or internal information.

## Vulnerability
- **Type:** Sensitive Information Disclosure  
- **Severity:** High  
- **Component:** API Gateway + Lambda  

## Root Cause
The application returns full data objects without filtering or restricting fields.  
Sensitive or internal information is included in API responses even when not required.

## Exploit Overview
An attacker sends a normal request and observes that the response includes:
- additional user data  
- internal identifiers  
- unnecessary fields  

This allows unauthorized access to sensitive information.

## Reproduction Steps
See `commands.txt` for full steps.

## Impact
- Exposure of sensitive user data  
- Leakage of internal system information  
- Increased attack surface for further exploitation  

## Fix
- Limit response fields to only required data  
- Remove sensitive/internal fields  
- Implement proper output filtering  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, the response only contains necessary fields and no sensitive information is exposed.

## Screenshots
See `screenshots/` for:
- exposed data before fix  
- filtered response after fix  
