# NAT and Port Forwarding

## 1. What is NAT?

Network Address Translation (NAT) is a process in which a network device, commonly a router or firewall, modifies IP address information in packet headers as traffic passes between networks.

NAT is commonly used to allow devices on private networks to communicate with external networks using one or more public IP addresses.

## 2. Why is NAT Used?

NAT is commonly used to:

- Allow multiple devices to share a public IPv4 address.
- Reduce the need for individual public IPv4 addresses.
- Translate between private and public IP addressing.
- Control how internal network devices communicate with external networks.

## 3. Types of NAT

### Static NAT

Static NAT establishes a fixed, one-to-one mapping between a private IP address and a public IP address.

The mapping remains consistent.

### Dynamic NAT

Dynamic NAT maps private IP addresses to public IP addresses selected from a configured pool.

The mapping is assigned dynamically when communication is initiated.

### Port Address Translation (PAT)

PAT allows multiple internal devices to share a single public IP address by using different port numbers to distinguish their connections.

It is also commonly called NAT overload.

**Example:**

Multiple devices on a private network access the internet through the same public IP address. The router uses different source port numbers to keep their connections distinguishable.

## 4. Port Forwarding

Port forwarding is a configuration that directs incoming traffic received on a particular public IP address and port to a specified internal device and port.

It is commonly configured on routers and firewalls to make an internal service accessible from an external network.

**Example:**

A router receives incoming traffic on public port `8080` and forwards it to an internal web server at:

- Internal IP address: `192.168.1.100`
- Internal port: `80`

The router forwards matching traffic to that internal service.

## 5. NAT and Port Forwarding: Difference

| NAT | Port Forwarding |
|---|---|
| Translates IP address information. | Directs incoming traffic to a specified internal address and port. |
| Commonly enables internal devices to communicate with external networks. | Commonly enables external access to an internal service. |
| Can use static, dynamic or port-based translation. | Uses configured port and destination rules. |

## 6. Security and Investigation Relevance

Understanding NAT and port forwarding helps when analysing network activity.

Investigators and security analysts may need to:

- Understand why multiple internal devices can appear behind the same public IP address.
- Examine source and destination ports in network logs.
- Correlate NAT translation records with internal IP addresses.
- Identify services exposed through port-forwarding rules.
- Consider timestamps and port information when correlating connections.

**Important:** A public IP address alone may not identify the internal device responsible for a connection. NAT logs, source ports, timestamps and other supporting evidence may be required for accurate correlation.

## Learning Reference

- Original handwritten Phase 1 networking notes
- Professor Messer
- Jeremy's IT Lab
- Related documentation: [IP Addressing Fundamentals](ip-addressing-fundamentals.md)
