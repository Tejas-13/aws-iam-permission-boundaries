# AWS IAM Permission Boundaries Project

## Overview

This project demonstrates how AWS IAM Permission Boundaries restrict the maximum permissions a user can receive, even when highly privileged policies such as AdministratorAccess are attached.

The project validates effective permission evaluation using IAM Policy Simulator and AWS Console testing.

---

## AWS Services Used

- AWS IAM
- IAM Policy Simulator
- Amazon S3
- Amazon CloudWatch
- Amazon EC2

---

## Key Concepts Demonstrated

- IAM Permission Boundaries
- Effective Permissions
- AdministratorAccess restriction
- Least Privilege Access
- IAM Policy Evaluation Logic
- Security Governance
- Service-level permission restriction

---

## Project Scenario

Created an IAM user with:

- AdministratorAccess policy attached
- Custom Permission Boundary allowing only S3 and CloudWatch access

Result:
- S3 access works
- CloudWatch access works
- EC2 access is denied

This demonstrates that Permission Boundaries define the maximum permissions allowed for a user regardless of attached identity policies.

---

## User Configuration

### IAM User

- RAM

### Attached Policy

- AdministratorAccess

### Permission Boundary

- S3CloudWatchBoundary

---

## Testing Performed

### S3 Testing

Validated:
- Bucket creation
- Object upload
- S3 console access

Result:
- Allowed

---

### CloudWatch Testing

Validated:
- CloudWatch console access
- Metrics visibility
- Dashboard access

Result:
- Allowed

---

### EC2 Testing

Validated:
- EC2 console access
- Launch instance attempt

Result:
- Denied

---

## IAM Policy Simulator Validation

Simulated permissions for:

- EC2 RunInstances
- S3 CreateBucket
- CloudWatch ListMetrics

Results confirmed:

- S3 actions allowed
- CloudWatch actions allowed
- EC2 actions denied by Permission Boundary

---

## Key Learnings

- Permission boundaries limit maximum permissions
- Effective permissions are the intersection of identity policies and permission boundaries
- AdministratorAccess does not override permission boundaries
- Permission boundaries help prevent privilege escalation
- Permission boundaries can restrict access to specific AWS services only
- IAM Policy Simulator helps validate effective permissions

---

## Security Importance

Permission boundaries are commonly used in enterprise AWS environments to:

- Delegate IAM administration safely
- Restrict maximum permissions
- Prevent privilege escalation
- Enforce governance controls
- Limit access to approved AWS services

---

## Outcome

Successfully implemented and validated AWS IAM Permission Boundaries using AdministratorAccess and a custom S3CloudWatchBoundary policy to demonstrate effective permission restriction and policy evaluation behavior.
