# Fix Notes - Lesson 7

## Root Cause
The Lambda function had excessive IAM permissions, allowing access to more resources than required.

## Fix Applied
- Restricted IAM policy to minimal required actions
- Limited access to specific resources only
- Applied least privilege principle

## Why This Fix Works
- Prevents unnecessary access to sensitive data
- Reduces attack surface
- Ensures proper access control at the infrastructure level

## Result
- Unauthorized resource access is blocked
- Permissions are tightly controlled
