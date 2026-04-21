# Bonus 2: User Enumeration via Cognito

## Summary
This bonus demonstrates a User Enumeration vulnerability through AWS Cognito. The authentication process returns different responses for valid and invalid users, allowing attackers to identify existing accounts.

## Vulnerability
- **Type:** User Enumeration  
- **Severity:** Medium  
- **Component:** Cognito Authentication  

## Root Cause
The authentication system returns distinguishable responses depending on whether a username exists.

This allows attackers to infer valid usernames by analyzing responses.

## Exploit Overview
An attacker submits authentication requests with different usernames.  
By observing the responses, the attacker can determine which usernames are valid.

## Reproduction Steps
See `commands.txt` for steps.

## Impact
- Disclosure of valid usernames  
- Increased risk of targeted attacks  
- Facilitation of brute-force attempts  

## Fix
- Return generic authentication error messages  
- Avoid revealing whether a username exists  
- Implement rate limiting on authentication attempts  

See:
- `fix-notes.md`
- `code-changes/`

## Verification
After applying the fix, responses for valid and invalid users are identical.

## Screenshots
See `screenshots/` for:
- valid user response  
- invalid user response  
- fix implementation  
- post-fix unified response  
