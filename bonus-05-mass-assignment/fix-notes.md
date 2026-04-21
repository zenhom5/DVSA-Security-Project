# Fix Notes - Bonus 5

## Root Cause
The application accepted all user-provided fields without restriction.

## Fix Applied
- Implemented input allowlist
- Ignored unexpected fields
- Enforced strict validation

## Why This Fix Works
- Prevents unauthorized modification of sensitive attributes
- Ensures only intended fields are processed

## Result
- Additional fields are ignored
- Application behavior is secure
