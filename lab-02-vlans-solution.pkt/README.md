# Lab 2: VLANs & Inter-VLAN Routing

## Objective
Segment a network into two VLANs and enable communication between
them using router-on-a-stick.

## Topology
- 1 Router (4331)
- 1 Switch (2960)
- 4 PCs

## IP Plan
| Device | VLAN | IP | Gateway |
|--------|------|----|---------|
| PC0 | 10 (Sales) | 192.168.10.10/24 | 192.168.10.1 |
| PC1 | 10 (Sales) | 192.168.10.11/24 | 192.168.10.1 |
| PC2 | 20 (Engineering) | 192.168.20.10/24 | 192.168.20.1 |
| PC3 | 20 (Engineering) | 192.168.20.11/24 | 192.168.20.1 |

## Tasks
1. Create VLAN 10 (Sales) and VLAN 20 (Engineering) on the switch
2. Assign access ports: Fa0/1-2 to VLAN 10, Fa0/3-4 to VLAN 20
3. Configure the switch-to-router link as a trunk (Gig0/1)
4. Configure router sub-interfaces with 802.1q encapsulation
5. Assign IPs and gateways to all four PCs
6. Verify connectivity between VLANs with ping

## Verification
- `show vlan brief` on switch — confirm VLAN assignments
- `show interfaces trunk` on switch — confirm trunking on Gig0/1
- `show ip route` on router — see two connected networks
- Ping PC0 → PC2 should succeed (cross-VLAN)

## Files
- `lab-02-vlans-start.pkt` — begin here (blank config)
- `lab-02-vlans-solution.pkt` — reference solution