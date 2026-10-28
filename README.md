# Six-Router Enterprise Network Lab

**Static Routing | Centralized DHCP | SSH Remote Management**

## Overview

This project demonstrates the design and configuration of a multi-router network using six Cisco 2811 routers in Cisco Packet Tracer.

The network uses static routing to establish connectivity between routers and multiple LANs. Router R2 provides centralized DHCP services, while DHCP relay configuration allows clients on remote LANs to obtain IP configuration from the centralized DHCP pools. SSH was configured and successfully tested for remote administration of all six routers.

## Objectives

- Build a network using six interconnected Cisco 2811 routers.
- Understand static routing and manually configured routes.
- Connect multiple LANs and enable inter-network communication.
- Configure centralized DHCP pools on R2.
- Configure DHCP relay using `ip helper-address`.
- Enable and test SSH remote management on all six routers.
- Verify connectivity through ping tests.

## Lab Environment

- **Simulation platform:** Cisco Packet Tracer
- **Routers:** 6 × Cisco 2811
- **Inter-router connections:** Serial links
- **Routing method:** Static routing
- **DHCP server:** R2
- **Remote administration:** SSH
- **LANs:** Connected to R1, R3, R4, and R6

## Network Topology

The lab contains six routers, R1 through R6.

The documented links are:

- R1 — R2 and R4
- R2 — the other routers, as described in the lab notes
- R3 — R2 and R6
- R4 — R1, R5 and R2&#x20;
- R5 — R2, R4, and R6
- R6 — R2, R3, and R5

R1, R3, R4, and R6 connect to their own LANs.

**Topology note:** The exact link list and diagram should be verified against the original Packet Tracer file before publication because the recorded connections may contain overlaps or omissions.

## Implementation

### 1. Router Connectivity

Added six Cisco 2811 routers and interconnected them using serial cables to create a multi-router topology.

### 2. Static Routing

Configured static routes manually to understand how routers forward traffic between remote networks without using dynamic routing protocols such as OSPF or EIGRP.

### 3. LAN Configuration

Connected end devices to LANs behind R1, R3, R4, and R6. Configured the required addressing and static routes for communication between LANs.

### 4. Connectivity Testing

Performed ping tests to verify that the configured network paths worked successfully.

### 5. Centralized DHCP

Configured DHCP pools directly on R2 using the Cisco IOS `ip dhcp pool` command.

Configured `ip helper-address` on the appropriate router interfaces to relay DHCP requests from remote LANs to the centralized DHCP service.

### 6. SSH Remote Management

Configured SSH on all six routers and successfully tested remote access.

The configuration process included:

- Local usernames and passwords
- The domain name `host.local`
- RSA key generation
- VTY line configuration using `line vty 0 4`
- SSH access using `transport input ssh`

Exact command sequences and authentication settings should be added after reviewing the saved router configurations.

## Verification Results

| Test                                 | Status              |
| ------------------------------------ | ------------------- |
| Static routing                       | Configured          |
| Ping connectivity                    | Successful          |
| Centralized DHCP pools on R2         | Configured          |
| DHCP relay using `ip helper-address` | Configured          |
| SSH remote access to all six routers | Tested successfully |

Detailed IP addressing, DHCP lease evidence, and command outputs will be added after verification.

## Security Considerations

- SSH provides encrypted remote administration and is preferred over Telnet.
- Use strong, unique credentials for router administration.
- Restrict management access to authorized devices where possible.
- Do not publish real passwords, private keys, or sensitive configuration details.

## Future Improvements

- Add the final network topology diagram.
- Document all interface addresses and subnet masks.
- Include a table of static routes and next-hop addresses.
- Capture DHCP lease and client configuration evidence.
- Document SSH verification commands and results.
- Explore ACLs to control traffic between LANs.
- Add a troubleshooting section describing issues encountered and how they were resolved.

## Learning Outcomes

This project provided hands-on practice with static routing, multi-router connectivity, centralized DHCP, DHCP relay, and SSH remote administration in a simulated enterprise network.

## Project Files

- `README.md` — Project documentation
- `topology/` — Network topology diagram
- `packet-tracer/` — Original Packet Tracer file
- `screenshots/` — Configuration and verification evidence
- `configs/` — Sanitized configuration notes, when available

