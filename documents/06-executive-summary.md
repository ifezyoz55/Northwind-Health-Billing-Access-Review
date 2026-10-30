# 06 — Executive Summary
Project: Northwind Health | Billing RBAC  
Document Reference: IAM-RBAC-06-ES  
Version: 1.0  
Status: Completed — Portfolio Case Study  
Classification: Public — Fictional Data  

# 1. Overview
This assessment reviewed billing-system access assigned to six Northwind Health employees to determine whether their permissions aligned with their job responsibilities.

The review focused on role-based access control (RBAC), least privilege, segregation of duties, excessive permissions, 
and the potential business risks associated with inappropriate access.

# 2. Assessment Outcome
The review identified excessive access across several employee accounts, including financial permissions assigned to IT Support and permissions that were not supported by the supplied job descriptions.

A proposed RBAC model was developed to align system permissions with four defined roles: **Billing Clerk**, **Billing Supervisor**, **Finance Manager**, and **IT Support**.

# 3. Key Findings
| Employee | Key Finding |
|---|---|
| `Ana` | Billing data export access was not required for the stated Billing Clerk responsibilities. |
| `Ben` | Held refund approval and payee creation permissions beyond the stated Billing Clerk requirements. |
| `Chloe` | Existing access matched the stated Billing Clerk requirements. |
| `Dev` | Held payee creation and payment approval permissions beyond the stated Billing Supervisor requirements. |
| `Erin` | Held refund approval access not included in the stated Finance Manager requirements. |
| `Fraser` | Held all financial permissions alongside system administration access, creating the highest-priority access concern. |

Additional observation: **`Create New Payee`** had no established business requirement in the supplied role descriptions. It was therefore excluded from the proposed RBAC model pending business-owner approval.

# 4. Recommended Access Model
The proposed role structure applies the principle of least privilege:
| Role | Approved Permissions |
|---|---|
| Billing Clerk | Create invoices; edit billing details |
| Billing Supervisor | Billing Clerk permissions; approve refunds |
| Finance Manager | Approve payments; export billing data |
| IT Support | System administration only |

# 5. Remediation Priorities
The following actions are recommended:
- Validate
- Remediate
- Verify

IT Support should retain technical access only. Any temporary financial access needed for troubleshooting must be approved, time-limited, and logged.

# 6. Conclusion

Excessive access and poorly separated responsibilities can expose billing operations to financial and operational risks. Implementing the proposed RBAC model, regular access reviews, and preventive controls will strengthen access governance and accountability.

This is a fictional case study. No actual misuse was established, and no live systems or accounts were accessed or modified.

## Related Documents:
- [01 — Billing Access Review: Scope](01-billing-access-scope.md)
- [02 — RBAC Role Design and Access Gap](02-rbac-role-design-and-access-gap.md)
- [03 — Access Risk and Segregation of Duties](03-access-risk-and-segregation-of-duties.md)
- [04 — User Access Findings and Risk Register](04-user-access-findings-and-risk-register.md)
- [05 — Remediation, Rollout and Controls](05-remediation-rollout-and-controls.md)


