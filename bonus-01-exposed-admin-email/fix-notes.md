# Fix Notes - Bonus 1

## Root Cause
The application exposed sensitive information (admin email) in API responses.

## Fix Applied
- Removed admin email from responses
- Filtered sensitive fields
- Restricted internal data exposure

## Why This Fix Works
- Prevents leakage of sensitive information
- Reduces risk of targeted attacks

## Result
- Admin email is no longer visible
- Responses are sanitized
