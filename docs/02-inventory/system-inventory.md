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
| SYS-001 | Payment processor | Authorize subscription payments and process refunds | Finance Director | Third-party SaaS | Simulated payment API using test data only | High |
| SYS-002 | Customer portal | Allow subscribers to manage accounts and subscriptions | Product Director | Internally managed cloud application | Demo web application on a Linux VM or container | High |
| SYS-003 | Identity provider | Authenticate users and enforce access policies | Chief Information Security Officer | Internally managed identity service | Authentik or Keycloak on a dedicated VM/container | High |
| SYS-004 | Subscription database | Store subscriber, plan, and subscription records | Subscription Operations Director | Managed database service | MySQL on a restricted VM/container | High |
| SYS-005 | Support-ticket system | Record, assign, and resolve customer issues | Customer Support Director | Third-party SaaS | Zammad or GLPI on a VM/container | Medium |
| SYS-006 | Analytics platform | Measure product usage and subscription trends | Data and Analytics Director | Third-party SaaS | Matomo on a VM/container using synthetic events | Medium |
| SYS-007 | Marketing automation platform | Manage permitted campaigns and renewal communications | Marketing Director | Third-party SaaS | Mautic on a VM/container using synthetic contacts | Medium |
| SYS-008 | Email delivery service | Deliver account, billing, security, and support messages | Customer Communications Director | Third-party SaaS | Mailpit for local capture of synthetic email | High |
| SYS-009 | Security logging and SIEM | Centralize security events and support incident detection | Chief Information Security Officer | Internally managed security platform | Wazuh server and agent deployment | High |
| SYS-010 | Backup and recovery system | Restore critical systems and information after loss or failure | IT Operations Director | Internally managed infrastructure service | Proxmox Backup Server or encrypted backup repository | Critical |
| SYS-011 | Cloud infrastructure | Host Blue Arbor applications, networks, and data services | Infrastructure Director | Infrastructure as a Service | Proxmox or another hypervisor and segmented virtual networks | Critical |



## 2. Data and compliance details

| System ID | Data subjects | Data categories | Retention or deletion rule | External recipients | PCI DSS | GDPR | CCPA | NIST CSF notes |
|---|---|---|---|---|---|---|---|---|
| SYS-001 | Subscribers and payment account holders | Billing contact, payment token, card brand, last four digits, transaction history | Based on transaction, dispute, accounting, and legal requirements; exact period TBD | Payment processor and financial institutions | Potentially in scope; architecture review required | Personal and financial data processing | Consumer and sensitive personal information may be involved | Govern third parties; protect data; detect and respond to payment incidents |
| SYS-002 | Subscribers and authorized account users | name, email, account ID, subscription status, account activity. | deleted after account closure | Cloud hosting provider, identity provider, payment processor. | potentially in scope | processes account and preference data to provide the subscription service | includes identifiers, commercial info, account activity and preferences, disclosure must be documented | protect accounts and data, manage IAM, log sec events and respond to unauthorized access |
| SYS-003 | Customers, subscribers, admins | Name, email, account ID, password hash, MFA config, roles, permission, IP | accounts are disabled and active sessions revoked following account closure or admin departure. account data is deleted after a defined period TBD | None | Potentially in scope depending on if the identity provider authenticates payment related systems | Processes user names, credentials, roles and authentication activity to authenticate users and allocate permissions | processes user names and account IDs to allocate permissions | protect identities and access, detect malicious authentication activity, and respond to compromised accounts or credentials |
| SYS-004 | people with subscriptions | name, account ID number | For activity analysis we retain user subscription data to show trends in subscriptions and to give customers a clear guide for decision making | none | not in scope | processes identifying data about a person to assign the subscription they paid for | not in scope | Protect user identifying data and detect malicious entries into the database. |
| SYS-005 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-006 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-007 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-008 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-009 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-010 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |
| SYS-011 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |

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
