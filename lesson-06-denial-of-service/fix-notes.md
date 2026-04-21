# Fix Notes - Lesson 6

## Root Cause
The application did not enforce rate limiting or request throttling, allowing unlimited requests.

## Fix Applied
- Implemented rate limiting
- Added request throttling controls
- Restricted excessive requests

## Why This Fix Works
- Prevents abuse by limiting request frequency
- Protects system resources from exhaustion

## Result
- System remains stable under load
- Excessive requests are blocked or delayed
