# Fix Notes - Lesson 4

## Root Cause
The S3 bucket had overly permissive write access, allowing unauthorized uploads.  
The Lambda function processed files without validation.

## Fix Applied
- Restricted S3 bucket access (no public write)
- Limited access using IAM policies
- Validated file names and types
- Avoided unsafe processing of user-controlled input

## Why This Fix Works
- Prevents unauthorized uploads
- Ensures only trusted data is processed
- Eliminates attacker-controlled execution paths

## Result
- Malicious uploads are blocked
- Backend processing is secure
