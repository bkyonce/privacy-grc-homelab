# Network Baseline

This folder documents the current Blue Arbor homelab network before new systems or firewall rules are added.

## Files

- `opnsense-baseline.md` — Sanitized OPNsense interfaces, firewall policy, aliases, NAT, DNS, DHCP, and security-service notes
- `kali-baseline.md` — Planned record of the Kali testing workstation
- `network-diagram.md` — Planned high-level network and trust-boundary diagram

## Public-repository rules

Information stored here must be safe for a public portfolio.

### Safe to include

- Fictional asset identifiers
- Interface purposes and security zones
- Sanitized or example private networks
- Firewall-rule intent
- Service names and business justification
- Product versions when they do not expose a known vulnerable public service
- Findings, decisions, and remediation plans written without operational secrets

### Keep private

- Public WAN addresses
- Usernames and passwords
- API keys, VPN keys, certificates, and recovery codes
- Complete OPNsense configuration exports
- MAC addresses and hardware serial numbers
- Exact externally reachable management details
- University of Michigan information
- Screenshots containing secrets or identifiable external information

The exact operational configuration should remain in encrypted private storage. This repository contains only a sanitized representation suitable for learning and portfolio review.
