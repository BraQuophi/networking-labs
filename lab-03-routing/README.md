# Lab 3: Routing — Static and OSPF

## Objective
Connect three routers and enable end-to-end communication using
both static routes and OSPF dynamic routing.

## Topology
PC0 --- R1 --- R2 --- R3 --- PC1

## IP Plan
| Device | Interface | IP |
|--------|-----------|-----|
| PC0 | NIC | 10.0.1.10/24, GW 10.0.1.1 |
| R1 | Gig0/0/0 | 10.0.1.1/24 |
| R1 | Gig0/0/1 | 10.0.12.1/30 |
| R2 | Gig0/0/0 | 10.0.12.2/30 |
| R2 | Gig0/0/1 | 10.0.23.2/30 |
| R3 | Gig0/0/0 | 10.0.23.1/30 |
| R3 | Gig0/0/1 | 10.0.3.1/24 |
| PC1 | NIC | 10.0.3.10/24, GW 10.0.3.1 |

## Tasks
1. Assign IPs to all router interfaces and PCs
2. Add static routes on R1, R2, R3 for full reachability
3. Verify PC0 → PC1 ping works via static routes
4. Remove static routes and enable OSPF area 0 on all routers
5. Verify OSPF neighbors form and PC0 → PC1 ping works via OSPF

## Verification
- `show ip route` — see `S` routes (static phase) then `O` routes (OSPF phase)
- `show ip ospf neighbor` — adjacencies in FULL state
- Ping PC0 → PC1 should succeed in both phases

## Files
- `lab-03-routing-start.pkt` — begin here (IPs configured, no routing)
- `lab-03-routing-solution.pkt` — reference solution (OSPF configured)