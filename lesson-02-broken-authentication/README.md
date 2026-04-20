# Lesson 2: Broken Authentication

## Summary
This lesson demonstrates a Broken Authentication vulnerability in the DVSA application. The backend trusted JWT payload claims without verifying the signature, allowing an attacker to impersonate another user.

## Vulnerability
- **Type:** Broken Authentication (JWT Validation Failure)  
- **Severity:** Critical  
- **Component:** API Gateway + Lambda  
- **Mechanism:** Unverified JWT claims  

## Root Cause
The application decodes JWT tokens and directly trusts fields such as `username` and `sub` without verifying the token signature.

Because no signature validation is performed, an attacker can modify the token payload and impersonate any user.

## Exploit Overview
An attacker:
1. Extracts their own JWT  
2. Modifies the payload to match a victim user  
3. Reuses the original signature  
4. Sends the forged token  

The backend accepts the token and returns victim data.

## Reproduction Steps
See `commands.txt` for full steps.

## Impact
- Account impersonation  
- Unauthorized data access  
- Full bypass of authentication controls  

## Fix
Implemented proper JWT verification using Cognito JWKS:
- Validate signature  
- Validate issuer (`iss`)  
- Validate expiration (`exp`)  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, the forged token is rejected:

```json
{"status":"err","msg":"invalid token"}
