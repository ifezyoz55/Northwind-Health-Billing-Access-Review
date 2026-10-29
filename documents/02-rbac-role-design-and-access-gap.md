# 02 — RBAC Role Design and Access Gap
Project: Northwind Health | Billing Access Review  
Document Reference: IAM-RBAC-02-RD  
Version: 1.0  
Status: Draft — Portfolio Case Study  
Classification: Public — Fictional Data  

# 1. Current Access Matrix
The matrix below shows the permissions assigned to each employee before remediation.
| Employee | Job Title | Create Invoices | Approve Refunds | Edit Billing Details | Create New Payee | Approve Payments | Export Billing Data | System Admin |
|---|---|---|---|---|---|---|---|---|
| Ana | Billing Clerk | ✓ | — | ✓ | — | — | ✓ | — |
| Ben | Billing Clerk | ✓ | ✓ | ✓ | ✓ | — | — | — |
| Chloe | Billing Clerk | ✓ | — | ✓ | — | — | — | — |
| Dev | Billing Supervisor | ✓ | ✓ | ✓ | ✓ | ✓ | — | — |
| Erin | Finance Manager | — | ✓ | — | — | ✓ | ✓ | — |
| Fraser | IT Support | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

# 2. Proposed RBAC Role Design
Roles are defined according to the supplied job descriptions and the principle of least privilege.
| Permission | Billing Clerk | Billing Supervisor | Finance Manager | IT Support |
|---|---|---|---|---|
| Create invoices | ✓ | ✓ | — | — |
| Approve refunds | — | ✓ | — | — |
| Edit billing details | ✓ | ✓ | — | — |
| Create new payee | — | — | — | — |
| Approve payments | — | — | ✓ | — |
| Export billing data | — | — | ✓ | — |
| System administration | — | — | — | ✓ |

_Create New Payee remains unassigned pending confirmation of business need and approval._

#  3. Target Access Matrix
This is the proposed access after the new roles are applied.

| Employee | Job Title | Create Invoices | Approve Refunds | Edit Billing Details | Create New Payee | Approve Payments | Export Billing Data | System Admin |
|---|---|---|---|---|---|---|---|---|
| Ana | Billing Clerk | ✓ | — | ✓ | — | — | — | — |
| Ben | Billing Clerk | ✓ | — | ✓ | — | — | — | — |
| Chloe | Billing Clerk | ✓ | — | ✓ | — | — | — | — |
| Dev | Billing Supervisor | ✓ | ✓ | ✓ | — | — | — | — |
| Erin | Finance Manager | — | — | — | — | ✓ | ✓ | — |
| Fraser | IT Support | — | — | — | — | — | — | ✓ |

# 4. Access Gap Analysis
| Employee | Access to Remove | Reason |
|---|---|---|
| Ana | Export billing data | Not required for Billing Clerk duties. |
| Ben | Approve refunds; Create New Payee | Not established for the Billing Clerk role. |
| Chloe | None | Current access matches the stated requirements. |
| Dev | Create New Payee; Approve Payments | Payee creation is unapproved; payment approval is assigned to Finance. |
| Erin | Approve refunds | Not required by the supplied Finance Manager description. |
| Fraser | All financial permissions | IT Support requires technical administration, not routine financial access. |

# 5. Design Considerations
- Apply least privilege by granting only permissions required for each role.
- Separate financial activities that could create fraud or error risks.
- Confirm who requires Create New Payee before assigning it.
- Provide Fraser with approved, time-limited elevated access when troubleshooting requires it.

---
Next Document: 03-access-risk-and-segregation-of-duties.md
   
