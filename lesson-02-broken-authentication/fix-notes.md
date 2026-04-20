# Fix Notes - Lesson 2

## Root Cause
The application trusted JWT payload fields without verifying the token signature.

This allowed attackers to modify token contents and impersonate other users.

## Fix Applied
- Implemented JWT signature verification using Cognito JWKS
- Validated issuer (`iss`)
- Checked token expiration (`exp`)
- Ensured valid token type (`token_use`)

## Why This Fix Works
- Signature verification ensures token integrity
- Modified tokens fail verification
- Only valid tokens issued by Cognito are accepted

## Result
- Forged tokens are rejected
- User impersonation is no longer possible
