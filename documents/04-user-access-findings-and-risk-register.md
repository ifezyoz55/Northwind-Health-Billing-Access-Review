# 04 — User Access Findings and Risk Register
Project: Northwind Health | Billing Access Review  
Document Reference: IAM-RBAC-04-FR  
Version: 1.0  
Status: Draft — Portfolio Case Study  
Classification: Public — Fictional Data  

# 1. Access Findings
The review compares each employee's current permissions against the proposed role design 
to identify unnecessary access and potential business risks.

| Employee | Access to Remove | Reason | Priority |
|---|---|---|---|
| Ana | Export billing data | Not required for Billing Clerk duties; creates unnecessary access to billing data. | Medium |
| Ben | Approve refunds; Create New Payee | Neither permission is established for the Billing Clerk role. | Review Required |
| Chloe | None | Current access matches the stated requirements. | No Change |
| Dev | Create New Payee; Approve Payments | Payee creation is unassigned, and payment approval belongs to the Finance Manager role. | High |
| Erin | Approve refunds | Not required by the supplied Finance Manager description. | Medium |
| Fraser | All financial permissions | IT Support requires system administration, not routine financial access. | High — Highest Priority |

# 2. Risk Register
| Account | Risk | Potential Business Impact | Recommended Action |
|---|---|---|---|
| Ana | Unnecessary billing-data export access. | Sensitive billing information could be exported without a business need. | Remove export permission. |
| Ben | Unjustified refund and payee permissions. | Could enable inappropriate financial actions if the permissions are misused. | Remove both permissions unless an approved business need is established. |
| Dev | Payee creation and payment approval, alongside invoice creation. | Could enable fraudulent payments or reduce independent oversight. | Remove payee creation and payment approval. |
| Erin | Refund approval outside the stated role requirements. | Could allow refunds beyond the Finance Manager's defined responsibilities. | Remove refund approval. |
| Fraser | Financial permissions combined with system administration. | Broad access increases the potential impact of misuse and weakens separation between IT and finance. | Remove permanent financial permissions; retain system administration. |

# 3. Highest-Priority Finding
Fraser — IT Support

Fraser's combination of system administration and financial access creates the highest potential risk. Remove permanent financial permissions while retaining system administration. Grant temporary, approved, and logged access only when troubleshooting requires it.

---
Next Document: 05-remediation-rollout-and-controls.md
