# Networking Devices and Appliances

## Overview

Network devices perform different roles in communication, traffic forwarding, security, availability and resource access.

## 1. Router

A router forwards traffic between different IP networks or subnets.

- Operates primarily at OSI Layer 3.
- Uses IP addresses to make forwarding decisions.
- Connects different networks.
- May provide additional features such as NAT and firewall functionality.

**Key distinction:** A router forwards packets between networks; a switch primarily forwards frames within a local network.

## 2. Switch

A switch connects devices within a local network.

- Primarily operates at OSI Layer 2.
- Uses MAC addresses to forward Ethernet frames.
- Learns MAC addresses and associates them with switch ports.
- Reduces unnecessary forwarding by sending frames towards the appropriate destination port.

Some multilayer switches also provide Layer 3 routing functionality.

## 3. Firewall

A firewall controls network traffic according to configured security rules.

Common capabilities include:

- Filtering traffic by IP address, port and protocol.
- Allowing or blocking connections.
- Stateful traffic inspection.
- Application-aware filtering in advanced firewalls.
- Network Address Translation (NAT) in many implementations.

### Traditional and Next-Generation Firewalls

| Traditional firewall | Next-generation firewall |
|---|---|
| Primarily uses network and transport-layer information | Adds deeper inspection and application awareness |
| Filters using addresses, ports and protocols | May inspect applications and detect threats |
| Focuses on traffic control | Combines traffic control with additional security capabilities |

## 4. IDS and IPS

**IDS — Intrusion Detection System**

- Monitors network or system activity.
- Identifies suspicious or potentially malicious activity.
- Generates alerts for investigation.

**IPS — Intrusion Prevention System**

- Monitors activity and can take action against detected threats.
- May block or drop suspicious traffic.

| IDS | IPS |
|---|---|
| Primarily detects and alerts | Detects and can prevent |
| Often deployed for monitoring | Often deployed inline |
| Helps security teams investigate events | Can automatically enforce protective actions |

Detection does not automatically establish that an event is malicious; alerts require validation.

## 5. Load Balancer

A load balancer distributes incoming traffic across multiple servers.

### Purpose

- Distributes requests across available servers.
- Helps prevent one server from becoming overloaded.
- Supports scalability.
- Improves service availability when configured with health checks and appropriate redundancy.

### Common Features

- Configurable traffic distribution.
- TCP and application-layer load balancing.
- SSL/TLS offloading in supported configurations.
- Health monitoring and server failover.

**Example:** A web application may use several web servers behind one load balancer.

## 6. QoS and Traffic Prioritisation

Quality of Service (QoS) manages how network resources are allocated to different traffic types.

Common concepts:

- Traffic classification.
- Traffic prioritisation.
- Traffic shaping.
- Bandwidth management.

QoS is useful when applications have different network performance requirements, such as voice, video and ordinary data traffic.

## 7. Proxy Server

A proxy acts as an intermediary between a client and another server.

### How It Works

1. A client sends a request to the proxy.
2. The proxy processes or forwards the request.
3. The proxy communicates with the destination on the client's behalf.
4. The response is returned to the client.

### Common Uses

- Access control.
- Content filtering.
- Caching.
- Monitoring and logging.
- Hiding internal client addresses from external destinations in some configurations.

Some proxies are transparent to users, while others require explicit client configuration.

## 8. NAS and SAN

Both provide network-based storage, but they use different access approaches.

| NAS | SAN |
|---|---|
| Network Attached Storage | Storage Area Network |
| Provides file-level access | Provides block-level storage access |
| Commonly uses protocols such as SMB and NFS | Commonly uses Fibre Channel or iSCSI |
| Appears as shared network storage | Storage can be presented to servers as block devices |

### Key Difference

NAS is generally used for shared file access, while SAN provides block storage that servers can use to manage their own file systems.

## 9. Wireless Access Point (AP)

A wireless access point connects wireless devices to a wired network.

- Bridges wireless and wired network connectivity.
- Primarily performs Layer 2 bridging.
- Is not necessarily a router.
- Multiple access points can provide wireless coverage across a building or site.

### Wireless Infrastructure

Larger networks may deploy multiple access points across different locations.

Important considerations include:

- Consistent access policies.
- Wireless security configuration.
- Access point management.
- Seamless connectivity when supported by the network design.

A wireless router commonly combines routing and access point functionality in one device.

## Security and Investigation Relevance

Understanding these devices helps identify where network traffic is forwarded, filtered, monitored, distributed or stored.

During investigations, their logs and configurations may help establish:

- Which devices communicated.
- Whether traffic was allowed or blocked.
- Whether suspicious activity generated alerts.
- Which server handled a request.
- How network access was controlled.

---

## Learning Reference

- Professor Messer
- Jeremy's IT Lab
- Original handwritten Phase 1 networking notes
