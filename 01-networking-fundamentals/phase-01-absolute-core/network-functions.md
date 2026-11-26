# Network Functions

## 1. Content Delivery Network (CDN)

A CDN improves content delivery using geographically distributed caching servers.

- Stores copies of content at different locations.
- Users can receive cached content from a nearby server.
- Reduces the distance data needs to travel.
- Commonly used by large websites.
- Its operation is generally invisible to end users.

**Purpose:** Faster and more efficient content delivery.

## 2. Virtual Private Network (VPN)

A VPN provides secure communication across a public network such as the internet.

- Uses encryption to protect data in transit.
- Supports private communication over an otherwise untrusted network.
- Can be implemented through specialised hardware or software.
- May be integrated into firewalls.
- Often uses client software, sometimes built into an operating system.

**Purpose:** Protect data while it travels across public networks.

## 3. Quality of Service (QoS)

QoS manages network traffic and controls how network resources are used.

Important concepts:

- **Traffic shaping:** Controls the rate at which traffic is sent.
- **Packet shaping:** Regulates packet transmission.
- **Bandwidth management:** Controls or allocates available bandwidth and data rates.

QoS can be implemented through routers, switches, firewalls and dedicated QoS devices.

**Purpose:** Manage traffic and prioritise network resources according to requirements.

## 4. Time to Live (TTL)

TTL limits how long an IP packet can continue travelling through a network.

For IPv4:

- The sender assigns an initial TTL value.
- Each router forwarding the packet decreases the value by at least one.
- When the TTL reaches zero, the packet is discarded.
- This prevents packets from circulating indefinitely because of routing loops.

**Purpose:** Prevent packets from remaining in the network indefinitely.

---

## Security and Investigation Relevance

- **CDN:** Helps understand distributed web infrastructure and content delivery.
- **VPN:** Important when analysing encrypted network connections and remote access.
- **QoS:** Helps explain traffic prioritisation and bandwidth behaviour.
- **TTL:** Useful when examining packet captures and diagnosing network paths.

## Learning Reference

- Professor Messer
- Jeremy's IT Lab
- Original handwritten Phase 1 networking notes
