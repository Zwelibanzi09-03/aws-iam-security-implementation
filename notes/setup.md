# IAM Security Setup Notes

## Overview

This project focused on setting up IAM users, groups, and policies to control access to AWS resources.

The goal was to understand how permissions work in real scenarios and test whether access is correctly allowed or denied.

---

## Users Created

- S3 Read-Only User
- Limited Access User

Each user was created separately to test different permission levels.

---

## Groups Created

- S3-ReadOnly-Group
- Limited-Access-Group

Users were added to groups instead of assigning permissions directly.  
This makes access easier to manage and scale.

---

## Policies Used

- AmazonS3ReadOnlyAccess (AWS managed policy)
- Custom restrictions for limited access user

Policies were attached to groups to control what users can and cannot do.

---

## Access Testing

### S3 Read-Only User

- Able to:
  - View S3 buckets
  - List objects
- Not able to:
  - Upload files
  - Delete objects

### Limited Access User

- Restricted from performing actions outside assigned permissions
- Used to confirm that access control is working correctly

---

## Bucket Testing

A test S3 bucket was used to verify access.

- Read-only user could view contents
- Delete actions were denied as expected

---

## Permission Behavior Observed

- Policies take effect immediately after assignment
- Denied actions return clear error messages
- Access depends fully on the policy attached to the user or group

---

## MFA Setup

Multi-Factor Authentication (MFA) was enabled to improve security.

This adds an extra layer of protection beyond just username and password.

---

## Key Takeaways

- Always assign permissions using groups instead of directly to users
- Follow least privilege (only give access that is needed)
- Test permissions after setup to confirm behavior
- MFA is important for securing accounts
