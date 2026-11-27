
# DHCP, APIPA and NAT

## 1. DHCP (Dynamic Host Configuration Protocol)

DHCP automatically assigns network configuration to devices, reducing the need for manual configuration.

A DHCP server can provide:
- IP address
- Subnet mask
- Default gateway
- DNS server address
- Lease duration

### DHCP DORA Process

DHCP commonly follows a four-step process known as DORA:

1. **Discover:** The client broadcasts a request to locate a DHCP server.
2. **Offer:** The DHCP server offers an available IP address and configuration.
3. **Request:** The client requests the offered IP address.
4. **Acknowledge:** The server confirms the allocation, and the client can use the configuration.

DHCP uses UDP:
- Server: Port 67
- Client: Port 68

## 2. APIPA (Automatic Private IP Addressing)

APIPA allows a device to automatically assign itself a link-local IPv4 address when it cannot obtain an address from a DHCP server.

- Address range: `169.254.0.0/16`
- Subnet mask: `255.255.0.0`
- Commonly assigned when DHCP configuration fails.
- Devices with APIPA addresses can communicate with compatible devices on the same local network.
- APIPA addresses are not routed across networks.

Before using an automatically selected address, the device checks that the address is not already in use.

**Troubleshooting significance:** If a Windows system has an address beginning with `169.254`, it can indicate that the system did not successfully obtain an address from DHCP.

## 3. DHCP Reservation

A DHCP reservation is a configuration on the DHCP server that consistently assigns a particular IP address to a device based on its MAC address or another client identifier.

- Helps a device receive the same IP address whenever it requests an address.
- Centrally managed through the DHCP server.
- Useful for devices that need predictable IP addresses, such as printers and servers.

## 4. NAT (Network Address Translation)

NAT translates IP addresses as traffic passes between networks.

It is commonly used by routers to allow devices using private IPv4 addresses to communicate with external networks through a public IP address.

### Why NAT is used

- Conserves public IPv4 addresses.
- Allows multiple devices on a private network to access the internet.
- Translates internal private addresses for communication with external networks.

### Private IPv4 Address Ranges

| Private range | CIDR |
|---|---|
| `10.0.0.0 – 10.255.255.255` | `10.0.0.0/8` |
| `172.16.0.0 – 172.31.255.255` | `172.16.0.0/12` |
| `192.168.0.0 – 192.168.255.255` | `192.168.0.0/16` |

Private IPv4 addresses are not directly routable over the public internet.

### Common NAT Types

- **Static NAT:** Maps one private IP address to one public IP address.
- **Dynamic NAT:** Maps private addresses to available public addresses from a configured pool.
- **PAT (Port Address Translation):** Allows multiple private devices to share a public IP address by using different port numbers. It is also commonly called NAT overload.

## 5. Related Concept: Port Forwarding

Port forwarding is a router configuration that directs incoming traffic on a specified port to a particular internal device and port.

For example, a router may forward incoming TCP traffic on port `443` to an internal web server.

Port forwarding can make an internal service reachable from outside the local network. It should be configured carefully because exposing services can increase security risks.

## Key Takeaways

- DHCP automatically provides IP configuration to network devices.
- DORA stands for Discover, Offer, Request and Acknowledge.
- APIPA uses the `169.254.0.0/16` link-local address range.
- DHCP reservation helps a device consistently receive a specific IP address.
- NAT translates IP addresses between networks.
- PAT allows multiple private devices to share a public IPv4 address.
- Port forwarding directs incoming traffic to a specified internal service.
