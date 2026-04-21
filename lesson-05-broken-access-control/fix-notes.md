# Fix Notes - Lesson 5

## Root Cause
The application did not verify that the requested resource belongs to the authenticated user.

## Fix Applied
- Added ownership validation
- Compared authenticated user ID with resource owner ID
- Rejected unauthorized access attempts

## Why This Fix Works
- Ensures users can only access their own data
- Prevents horizontal privilege escalation

## Result
- Unauthorized access is blocked
- Data isolation is enforced
