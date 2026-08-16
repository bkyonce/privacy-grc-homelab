# OPNsense Network Baseline

| Field | Value |
|---|---|
| Asset ID | NET-001 |
| System | OPNsense Firewall |
| Owner | Infrastructure Director |
| Version | TODO |
| Hypervisor | TODO |
| Primary purpose | Network routing, segmentation, and firewall enforcement |
| Review date | YYYY-MM-DD |
| Status | Working draft |

## Interfaces

| Interface | Purpose | Device | Sanitized network | VLAN | Addressing | Enabled |
|---|---|---|---|---|---|---|
| WAN | Internet connection | TODO | REDACTED | None | DHCP/Static | Yes |
| LAN | TODO | TODO | TODO | TODO | Static | Yes |
| OPT1 | TODO | TODO | TODO | TODO | Static | TODO |

## Firewall rules

Record meaningful user-created rules in evaluation order. Do not copy credentials, public addresses, or unnecessary automatic rules.

| Order | Interface | Action | Protocol | Source | Destination | Port | Logging | Business justification |
|---|---|---|---|---|---|---|---|---|
| 1 | TODO | TODO | TODO | TODO | TODO | TODO | TODO | TODO |

## Aliases

| Alias | Type | Purpose | Used by |
|---|---|---|---|
| TODO | Host/Network/Port | TODO | TODO |

## NAT and external exposure

| Type | Interface | Protocol | External port | Internal destination | Source restricted? | Purpose |
|---|---|---|---|---|---|---|
| TODO | TODO | TODO | TODO | REDACTED | TODO | TODO |

If no inbound port forwarding exists, write: `No inbound port forwards observed as of YYYY-MM-DD.`

## DHCP and DNS

| Service | Enabled | Interfaces | Purpose | Important notes |
|---|---|---|---|---|
| DHCP | TODO | TODO | Assign client addresses | Do not record MAC addresses |
| Unbound DNS | TODO | TODO | Internal DNS resolution | TODO |

## Other security services

| Service | Enabled | Interfaces or scope | Purpose | Important notes |
|---|---|---|---|---|
| VPN | TODO | TODO | Remote access | Do not record keys or endpoints |
| IDS/IPS | TODO | TODO | Detect or block suspicious traffic | TODO |
| Firewall logging | TODO | TODO | Support monitoring and investigations | TODO |
| Configuration backup | TODO | Local/private storage | Recover firewall configuration | Never upload the export |

## Current network relationships

Describe the existing architecture without including public addresses or secrets.

- OPNsense WAN connects to: TODO
- OPNsense LAN connects to: TODO
- Kali VM is located on: TODO
- Other known networks or systems: TODO
- Traffic allowed between internal networks: TODO

## Security observations

- Internet-facing services: TODO
- Network segmentation present: TODO
- Default-deny policy present: TODO
- Administrative access restrictions: TODO
- Firewall-rule logging: TODO
- Backup process: TODO
- Known weaknesses or questions: TODO

## Collection notes

Record where each fact came from.

| Date | OPNsense page or source | Information reviewed | Recorded by |
|---|---|---|---|
| YYYY-MM-DD | Interfaces > Assignments | Interface configuration | Buturo Bartolomei |

## Completion checklist

- [ ] Version and hypervisor are documented.
- [ ] Every assigned interface is listed.
- [ ] Public WAN information is redacted.
- [ ] Meaningful firewall rules are summarized in order.
- [ ] Aliases and NAT exposure are documented.
- [ ] DHCP and DNS services are identified.
- [ ] Existing Kali placement is recorded.
- [ ] No configuration exports, secrets, or sensitive screenshots were uploaded.
