
# DVSA Security Assessment Project

This repository contains my security analysis of the Damn Vulnerable Serverless Application (DVSA), conducted as part of a cybersecurity course project.

The project focuses on identifying, exploiting, and fixing vulnerabilities in a serverless AWS environment.

---

## Project Overview

This project includes:

- 10 core vulnerability lessons
- 7 additional bonus vulnerabilities
- Exploitation steps and commands
- Root cause analysis
- Fix implementations
- Verification after remediation
- Screenshots demonstrating each stage

---

## Technologies Used

- AWS (Lambda, API Gateway, DynamoDB, S3, Cognito, IAM)
- Node.js
- curl & jq
- JSON / REST APIs

---

## Repository Structure


DVSA-security-project/
│
├── report/
├── slides/
├── demos/
├── common/
│
├── lesson-01-event-injection/
├── lesson-02-broken-authentication/
├── lesson-03-sensitive-information-disclosure/
├── lesson-04-insecure-cloud-configuration/
├── lesson-05-broken-access-control/
├── lesson-06-denial-of-service/
├── lesson-07-over-privileged-functions/
├── lesson-08-logic-vulnerabilities/
├── lesson-09-vulnerable-dependencies/
├── lesson-10-unhandled-exceptions/
│
├── bonus-01-exposed-admin-email/
├── bonus-02-user-enumeration-via-cognito/
├── bonus-03-missing-rate-limiting-auth/
├── bonus-04-unprotected-admin-orders-endpoint/
├── bonus-05-mass-assignment/
├── bonus-06-verbose-error-messages/
└── bonus-07-unauthenticated-feedback-upload/




---

## How to Use This Repository

Each lesson and bonus folder contains:

- `README.md` → vulnerability explanation  
- `commands.txt` → reproduction steps  
- `fix-notes.md` → remediation details  
- `code-changes/` → before & after code  
- `screenshots/` → evidence  

A user can follow each folder independently to understand:

1. The vulnerability  
2. How it was exploited  
3. How it was fixed  
4. How the fix was verified  

---

## Security Note

This project was conducted in a controlled, intentionally vulnerable environment for educational purposes only.

All sensitive data such as tokens, API URLs, and identifiers have been replaced with placeholders.

Do not attempt to use these techniques on real systems without proper authorization.

---

## Author

Senior Computer Scince Student  
KFUPM
