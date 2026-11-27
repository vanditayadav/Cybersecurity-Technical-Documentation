# DNS and Caching

## 1. Domain Name System (DNS)

DNS translates human-readable domain names into IP addresses so that clients can locate network services.

**Example:**

A user enters a domain name in a browser. DNS helps resolve that name to an IP address used to reach the destination.

### DNS Lookup

1. A client needs the IP address associated with a domain.
2. It checks available local or cached DNS information.
3. If no valid cached answer is available, it queries a DNS resolver.
4. The resolver obtains the required answer.
5. The result can be cached for future use.

### DNS Caching

DNS caching temporarily stores lookup results to reduce repeated queries.

- Reduces unnecessary DNS lookups.
- Can improve response time.
- Avoids repeatedly querying upstream DNS servers for the same answer.
- Cached records are retained according to their TTL.

## 2. DNS TTL

DNS record TTL (Time to Live) specifies how long a DNS answer may be cached, generally in seconds.

For example, a DNS record with a TTL of 3600 seconds can be cached for up to one hour.

When the TTL expires, the cached record should no longer be treated as valid and a fresh lookup may be required.

## 3. Two Different Meanings of TTL

| IPv4 TTL | DNS Record TTL |
|---|---|
| Limits packet lifetime across routers | Controls how long DNS information may be cached |
| Decremented by routers during forwarding | Counts down while a DNS answer is cached |
| Helps prevent indefinite packet circulation | Helps control DNS cache freshness |

**Important:** IPv4 TTL and DNS TTL serve different purposes.

## Security and Investigation Relevance

DNS information can help investigators understand domain resolution, identify contacted infrastructure and interpret network activity.

DNS cache duration also matters when examining why a device may continue using a previously resolved IP address.

---

## Learning Reference

- Original handwritten Phase 1 networking notes
- Professor Messer
- Jeremy's IT Lab
