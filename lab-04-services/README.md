# Lab 4: Network Services — DHCP, DNS, and ACLs

## Objective
Configure automatic IP assignment (DHCP), name resolution (DNS),
and traffic filtering (ACLs) to secure a network.

## Topology
- 1 Router (ISR 4331)
- 1 Switch (2960)
- 1 Server
- 3 PCs

## IP Plan & VLANs
| Device | VLAN | IP | Gateway |
|--------|------|----|---------|
| Router (LAN) | 1 | 192.168.1.1/24 | - |
| Router (DMZ)| 2 | 192.168.2.1/24 | - |
| Router (Restricted) | 30 | 192.168.30.1/24 | - |
| Server | 2 | 192.168.2.100/24 | 192.168.2.1 |
| PC0 | 1 | DHCP (192.168.1.x) | 192.168.1.1 |
| PC1 | 1 | DHCP (192.168.1.x) | 192.168.1.1 |
| PC2 | 30 | 192.168.30.10/24 | 192.168.30.1 |

## Tasks
1. Configure the router with sub-interfaces for VLANs 1, 2, and 30
2. Configure DHCP on the router for the PC network (VLAN 1)
3. Configure the Server with a static IP, and enable DNS for `ghanaunion.local`
4. Apply an ACL to block PC2 (VLAN 30) from accessing the Server, while allowing PC0 and PC1
5. Verify PC0 can ping the server, but PC2 cannot

## Verification
- PCs in VLAN 1 get IPs automatically via DHCP
- `ping ghanaunion.local` resolves and succeeds on PC0
- PC2 cannot reach the Server (ACL blocks it)

## Files
- `lab-04-services-start.pkt` — begin here (DHCP, DNS, ACLs removed)
- `lab-04-services-solution.pkt` — reference solution