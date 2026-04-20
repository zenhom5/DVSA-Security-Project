# Lesson 4: Insecure Cloud Configuration

## Summary
This lesson demonstrates an Insecure Cloud Configuration vulnerability in the DVSA application. The S3 bucket is overly permissive, allowing unauthorized file uploads that are later processed by a Lambda function without validation.

## Vulnerability
- **Type:** Insecure Cloud Configuration  
- **Severity:** Critical  
- **Component:** S3 + Lambda  

## Root Cause
The S3 bucket allows unauthorized write access, and the backend Lambda function processes uploaded files without validating their content or names.

This creates a chain where attacker-controlled input is trusted and executed.

## Exploit Overview
An attacker uploads a malicious file to the S3 bucket.  
The Lambda function is triggered and processes the file without validation, potentially leading to unintended behavior or command execution.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Unauthorized file uploads  
- Potential command execution  
- Compromise of backend processing  

## Fix
- Restrict S3 bucket permissions  
- Remove public write access  
- Validate file names and types  
- Avoid executing commands using user-controlled data  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, unauthorized uploads are blocked and malicious files are rejected or safely handled.

## Screenshots
See `screenshots/` for:
- upload attempt  
- processing behavior  
- fix  
- verification  
