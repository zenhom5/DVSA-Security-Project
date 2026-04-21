# Lesson 6: Denial of Service (DoS)

## Summary
This lesson demonstrates a Denial of Service (DoS) vulnerability in the DVSA application. The backend does not implement rate limiting or request validation, allowing attackers to send excessive requests and degrade system performance.

## Vulnerability
- **Type:** Denial of Service (DoS)  
- **Severity:** High  
- **Component:** API Gateway + Lambda  

## Root Cause
The application processes incoming requests without any rate limiting, throttling, or input constraints.  
This allows attackers to overwhelm the system with repeated or heavy requests.

## Exploit Overview
An attacker sends a large number of requests in a short period of time.  
The system attempts to process all requests, leading to performance degradation or service disruption.

## Reproduction Steps
See `commands.txt` for full steps.

## Impact
- Service slowdown or unavailability  
- Resource exhaustion  
- Increased cost in serverless environments  

## Fix
- Implement rate limiting  
- Add request throttling  
- Validate input size and frequency  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, excessive requests are limited or rejected by the system.

## Screenshots
See `screenshots/` for:
- normal response  
- high request load  
- fix implementation  
- post-fix throttling  
