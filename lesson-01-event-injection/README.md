# Lesson 1: Event Injection

## Summary
This lesson demonstrates a critical Event Injection vulnerability in the DVSA application that leads to Remote Code Execution (RCE). The issue arises from insecure deserialization using the `node-serialize` library in the `DVSA-ORDER-MANAGER` Lambda function.

## Vulnerability
- **Type:** Event Injection / Insecure Deserialization  
- **Severity:** Critical  
- **Component:** DVSA-ORDER-MANAGER (AWS Lambda)  
- **File:** order-manager.js  

## Root Cause
The application deserializes user-controlled input using the `node-serialize` library. This library allows execution of JavaScript functions embedded in JSON using the `$$ND_FUNC$$` marker.

Because no validation or sanitization is applied, an attacker can inject executable code through the request.

## Exploit Overview
An attacker sends a malicious payload containing a `$$ND_FUNC$$` function via the API endpoint.  
The Lambda function processes it and executes the injected code.

## Reproduction Steps
See `commands.txt` for full commands.

## Impact
- Remote Code Execution (RCE)
- Access to Lambda environment
- Potential access to backend services and credentials

## Fix
- Removed `node-serialize`
- Replaced with `JSON.parse()`
- Added input validation

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, the same payload is rejected:

```json
{"status":"err","msg":"Invalid request format"}
