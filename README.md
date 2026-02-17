# AWS Secure IAM Lab

## Objective

Design and implement a least-privilege IAM environment in AWS using role-based access control, scoped policies, and access validation testing.

This lab focuses on building a production-style IAM foundation aligned with cloud security best practices.

---

## Architecture Overview

This lab includes:

- IAM users and groups
- Custom JSON policies
- EC2 instance role attachment
- S3 access scoping
- Intentional permission misconfiguration
- Policy remediation
- CloudTrail logging validation

---

## Security Focus

- Principle of Least Privilege
- Role-Based Access Control (RBAC)
- Policy scoping with explicit resource restrictions
- Testing and validating access boundaries
- Avoiding credential hardcoding
- Audit logging through CloudTrail

---

## Implementation Steps

1. Created IAM user groups (Dev, Ops).
2. Built custom JSON policies with restricted S3 access.
3. Attached IAM role to EC2 instance instead of using static credentials.
4. Intentionally broke access permissions to simulate misconfiguration.
5. Analyzed error responses and adjusted policy statements.
6. Verified access changes via AWS Console and CLI.
7. Confirmed API activity logging in CloudTrail.

---

## Sample Policy Snippet (Sanitized)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:GetObject"],
      "Resource": "arn:aws:s3:::example-bucket/*"
    }
  ]
}
