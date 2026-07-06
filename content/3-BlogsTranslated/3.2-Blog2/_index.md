---
title: "Building Secure B2C Applications with Amazon Cognito and Amazon Verified Permissions"
date: 2026-06-16
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# Building Secure B2C Applications with Amazon Cognito and Amazon Verified Permissions

In modern B2C applications, user management is not limited to logging in but also includes fine-grained access control to specific resources.

Typically, the system must address two main challenges:
- **Authentication:** Verifying who the user is.
- **Authorization:** Determining what the user is allowed to do.

AWS recommends combining **Amazon Cognito** and **Amazon Verified Permissions** to separate these two concerns, making the system cleaner and more scalable.

---

## The Problem with the Traditional Approach

In many applications, authorization logic is often written directly in the code:
- Hard to scale as the number of roles increases.
- Hard to maintain when rules become complex.
- Prone to scattered authorization logic.

As the system grows larger, this approach is no longer appropriate.

---

## AWS Solution

AWS proposes a decoupled architecture:
- **Amazon Cognito:** Handles user authentication and issues JWT tokens.
- **Amazon Verified Permissions (AVP):** Evaluates access requests based on policies.

Instead of writing logic in the application code, we define policies separately using the **Cedar language** and let AVP handle the decisions.

---

## System Architecture Workflow

**(Insert image here: Architecture Diagram)**  
*Figure 1: Cognito + Verified Permissions Flow*

Basic processing flow:
1. User logs in via Amazon Cognito.
2. Cognito returns a JWT token.
3. The application sends requests containing the token.
4. The backend calls Amazon Verified Permissions.
5. AVP evaluates the policy.
6. Returns Allow / Deny.

---

## Supported Authorization Models

The solution supports multiple common authorization patterns:
- **Resource-based access:** Users can only access their own resources.
- **Role-based access (RBAC):** Access control based on user roles.
- **Hierarchical access:** Access hierarchy according to organizational structure.
- **Explicit deny:** Denials always take precedence.
- **Admin override:** Admins have elevated privileges.

---

## Key Benefits

This solution brings several distinct advantages:
- Separation of authentication and authorization.
- Reduced authorization logic within application code.
- Policy changes can be made without redeploying the system.
- Enhanced auditability and centralized permissions management.
- Well-suited for multi-tenant B2C / SaaS systems.

---

### Amazon Cognito Cost
- Billed based on **Monthly Active Users (MAU)**.
- Costs increase with the number of users.

### Amazon Verified Permissions Cost
- Billed based on the number of policy evaluation requests.
- More requests lead to higher costs.

- For small systems: costs remain low.
- For large systems: it is necessary to optimize AVP API calls.

---

### 1. Comparison with Code-Based Authorization

| Criteria | Code-based | Cognito + AVP |
|----------|------------|----------------|
| Maintenance | Hard | Easier |
| Scalability | Poor | Good |
| Audit | Hard | Clear |
| Rule Changes | Requires deployment | No deployment required |

---

### 2. Comparison with IAM

- IAM is suitable for system-to-system access control.
- AVP is designed for application/B2C authorization.

---

### 3. Testing Approaches

Testing can be carried out via:
- Unit testing Cedar policies.
- Role-based testing (Admin/User/Guest).
- Cognito to AVP integration tests.
- Scenario-based testing based on real-world use cases.

---

## Conclusion

Combining **Amazon Cognito** and **Amazon Verified Permissions** enables a modern approach to B2C systems:

> Separating authentication and authorization makes the system easier to scale and manage.

However, attention should be paid to cost optimization when the system generates a large volume of requests.

---

### Reference Sources
https://aws.amazon.com/blogs/security/building-secure-b2c-applications-with-fine-grained-access-control-using-amazon-cognito-and-amazon-verified-permissions/
