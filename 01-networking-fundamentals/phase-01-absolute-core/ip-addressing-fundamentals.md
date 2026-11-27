# IP Addressing Fundamentals

## 1. What is an IP Address?

An Internet Protocol (IP) address is a logical address assigned to a network interface to enable communication over an IP network.

Example IPv4 address:

`192.168.1.165`

An IP address helps identify the network interface and its location within an IP network.

## 2. IPv4 Address Structure

IPv4 uses a 32-bit address divided into four 8-bit sections called octets.

Example:

`192.168.1.165`

Each octet is represented in decimal, with a value from 0 to 255.

An IPv4 address contains:
- Network portion: identifies the network.
- Host portion: identifies an interface within that network.

The subnet mask or prefix length determines how these portions are divided.

## 3. Subnet Mask

A subnet mask identifies which bits of an IPv4 address belong to the network portion and which belong to the host portion.

Example:

| Address | Value |
|---|---|
| IP address | 192.168.1.165 |
| Subnet mask | 255.255.255.0 |
| CIDR prefix | /24 |
| Network address | 192.168.1.0 |

A `/24` prefix means the first 24 bits are the network portion.

## 4. Default Gateway

A default gateway is the router or Layer 3 device that forwards traffic from a local network to destinations outside that network when no more specific route is available.

Example:

`192.168.1.1`

The gateway address must be reachable on the local network.

## 5. Public and Private IPv4 Addresses

### Private IPv4 Ranges

Private IPv4 addresses are reserved for use within private networks. They are not globally routable on the public internet.

| Range | CIDR |
|---|---|
| 10.0.0.0 – 10.255.255.255 | 10.0.0.0/8 |
| 172.16.0.0 – 172.31.255.255 | 172.16.0.0/12 |
| 192.168.0.0 – 192.168.255.255 | 192.168.0.0/16 |

### Public IPv4 Addresses

Public IPv4 addresses are globally routable, subject to routing and allocation policies.

Private networks commonly use NAT to enable communication with external networks.

## 6. Special IPv4 Addresses

| Address / Range | Purpose |
|---|---|
| 127.0.0.0/8 | Loopback |
| 169.254.0.0/16 | Link-local addressing |
| 0.0.0.0 | Unspecified address; also used in particular configuration contexts |
| 255.255.255.255 | Limited broadcast |

### Important distinctions

- **Loopback:** Used by a device to communicate with itself.
- **Link-local:** IPv4 addresses in this range can be automatically assigned when normal address configuration is unavailable.
- **Limited broadcast:** Targets all hosts on the local network segment; routers do not forward it.

## 7. DHCP — Dynamic Host Configuration Protocol

DHCP automatically provides network configuration to clients.

It can provide:
- IP address
- Subnet mask
- Default gateway
- DNS server addresses

### DHCP DORA Process

1. **Discover:** Client broadcasts to locate DHCP servers.
2. **Offer:** A DHCP server offers an address and configuration.
3. **Request:** Client requests the offered configuration.
4. **Acknowledge:** Server confirms the lease.

DHCP reduces the need to configure each device manually.

### DHCP Reservation

A reservation allows a DHCP server to consistently assign a particular IP address to a client, commonly based on its MAC address or client identifier.

---

## Security and Investigation Relevance

IP addressing helps investigators:
- Identify source and destination addresses in network logs.
- Distinguish private, public and special-purpose addresses.
- Understand whether a device was configured through DHCP.
- Interpret network connections and packet captures.

An IP address alone does not identify a person or prove who was operating a device.

## Learning Reference

- Original handwritten Phase 1 networking notes
- Professor Messer
- Jeremy's IT Lab
