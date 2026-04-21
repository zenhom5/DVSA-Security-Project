
# Lesson 5: Broken Access Control

## Summary
This lesson demonstrates a Broken Access Control vulnerability in the DVSA application. The backend does not properly verify ownership of resources, allowing users to access data that does not belong to them.

## Vulnerability
- **Type:** Broken Access Control  
- **Severity:** Critical  
- **Component:** API Gateway + Lambda  

## Root Cause
The application retrieves resources (such as orders) based only on identifiers provided in the request without verifying that the requesting user owns the resource.

## Exploit Overview
An attacker sends a request with another user’s `order-id`.  
Since the backend does not check ownership, it returns the victim’s data.

## Reproduction Steps
See `commands.txt` for full steps.

## Impact
- Unauthorized data access  
- Exposure of other users’ information  
- Violation of data isolation  

## Fix
- Enforce ownership checks  
- Validate that the requested resource belongs to the authenticated user  
- Implement proper authorization logic  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, requests for resources not owned by the user are rejected.

Example response:
```json
{"status":"err","msg":"access denied"}
