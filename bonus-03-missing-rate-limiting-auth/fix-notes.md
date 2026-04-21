# Fix Notes - Bonus 3

## Root Cause
The authentication endpoint allowed unlimited login attempts without rate limiting.

## Fix Applied
- Implemented rate limiting
- Added request throttling
- Introduced temporary blocking after repeated failures

## Why This Fix Works
- Prevents brute-force attempts
- Limits abuse of authentication endpoint

## Result
- Excessive login attempts are restricted
- Authentication endpoint is protected
