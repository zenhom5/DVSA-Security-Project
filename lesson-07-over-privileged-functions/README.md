# Lesson 7: Over-Privileged Functions

## Summary
This lesson demonstrates an Over-Privileged Functions vulnerability in the DVSA application. The Lambda function is granted excessive IAM permissions, allowing it to access resources beyond what is required.

## Vulnerability
- **Type:** Over-Privileged IAM / Excessive Permissions  
- **Severity:** Critical  
- **Component:** AWS Lambda + IAM  

## Root Cause
The Lambda function has overly broad IAM permissions, such as full access to DynamoDB or S3, without restriction.

This violates the principle of least privilege and allows unintended access to sensitive resources.

## Exploit Overview
An attacker uses legitimate API functionality but leverages the Lambda’s excessive permissions to access data that should not be accessible.

Since the backend does not enforce strict access controls, it retrieves unauthorized data.

## Reproduction Steps
See `commands.txt` for full steps.

## Impact
- Unauthorized data access  
- Exposure of sensitive information  
- Increased risk of privilege escalation  

## Fix
- Apply least privilege principle  
- Restrict IAM policies to only required actions  
- Limit access to specific resources  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, access to unauthorized resources is denied.

## Screenshots
See `screenshots/` for:
- normal access  
- unauthorized data access  
- fix implementation  
- post-fix restriction  
