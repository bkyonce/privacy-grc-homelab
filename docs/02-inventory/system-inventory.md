# Blue Arbor System Inventory

| Field | Value |
|---|---|
| Owner | Buturo Bartolomei |
| Version | 0.1 |
| Status | Working draft |
| Date | YYYY-MM-DD |

## Purpose

This inventory identifies the systems Blue Arbor uses, why each system exists, who owns it, and what information it handles. I will use it later to create data-flow diagrams, determine compliance scope, and assess risk.

Use one system ID in both tables so the business and data details stay connected. If I do not know an answer yet, I will write `TBD` and add the question to the decision log.

## 1. System ownership and architecture

| System ID | System name | Business purpose | Business owner | Hosting or service model | Homelab equivalent | Criticality |
|---|---|---|---|---|---|---|
| SYS-001 | Payment processor | Authorize subscription payments and process refunds | Finance Director | Third-party SaaS | Simulated payment service | High |
| SYS-002 | Customer Portal | manage subscriber accounts | Product director | API hosted no cloud infrastructure internal managed | demo Web Application running on linux VM | High |
| SYS-003 | Identity provider | Authenticate Users | CSO | internally managed cloud identity service | Keycloak or authentik VM | High |
| SYS-004 | Subscription Database | document all users and their  subscription | Operations director | managed Database | MySQL running on restricted container/VM | Medium |
| SYS-005 | Support Ticket system | Organize customer issues and support methods | HR | Web Application | Web Application | Medium |
| SYS-006 | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-007 | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-008 | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-009 | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-0010 | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-011 | TODO | TODO | TODO | TODO | TODO | TODO |

### Column guidance

- **System ID:** A permanent identifier such as `SYS-001`.
- **System name:** The application, platform, database, device group, or infrastructure component.
- **Business purpose:** The specific result the system supports.
- **Business owner:** The role accountable for the business use of the system.
- **Hosting or service model:** On-premises, cloud infrastructure, internally managed application, or third-party SaaS.
- **Homelab equivalent:** The component in my lab that represents the fictional system.
- **Criticality:** Low, moderate, high, or critical based on business impact.

## 2. Data and compliance details

| System ID | Data subjects | Data categories | Retention or deletion rule | External recipients | PCI DSS | GDPR | CCPA | NIST CSF notes |
|---|---|---|---|---|---|---|---|---|
| SYS-001 | Subscribers and payment account holders | Billing contact, payment token, card brand, last four digits, transaction history | Based on transaction, dispute, accounting, and legal requirements; exact period TBD | Payment processor and financial institutions | Potentially in scope; architecture review required | Personal and financial data processing | Consumer and sensitive personal information may be involved | Govern third parties; protect data; detect and respond to payment incidents |
| SYS-002 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-003 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-004 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-005 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-006 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-007 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-008 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |

### Framework labels

For PCI DSS, use:

- `In scope`
- `Potentially in scope`
- `Out of scope based on current architecture`
- `Needs review`

For GDPR and CCPA, explain why the system processes covered personal information instead of writing only `Yes` or `No`.

For NIST CSF, identify the most relevant risk-management outcome. Detailed control mapping will happen later.

## 3. Systems to consider

Use this list as a prompt, but include only systems Blue Arbor actually needs:

- Customer or member portal
- Identity provider
- Payment processor
- Subscription database
- Merchant administration dashboard
- Analytics platform
- Marketing automation platform
- Support-ticket system
- Email delivery service
- Security logging or SIEM platform
- Employee directory
- Backup and recovery system
- Cloud infrastructure
- Source-code repository
- Vendor-management system

## 4. Questions to ask for every system

1. What business process stops if this system becomes unavailable?
2. Whose information does it process?
3. Does it store information, transmit it, or only provide access to it?
4. Which employees or vendors can access it?
5. Does it send information to another country or organization?
6. Is the information copied into logs or backups?
7. How is information corrected or deleted?
8. Could the system affect the security of the payment environment?
9. Who accepts the risk associated with the system?
10. What do I still need to verify?


## Completion checklist

- [ ] Every Blue Arbor service has at least one supporting system.
- [ ] Every system has a unique ID and an owner.
- [ ] Every system lists the data subjects and data categories it handles.
- [ ] Vendors and external recipients are identified.
- [ ] Retention is documented or marked for follow-up.
- [ ] PCI DSS, GDPR, CCPA, and NIST considerations are recorded.
- [ ] Each homelab component has a fictional business-system purpose.
- [ ] Unanswered questions have been added to the decision log.
