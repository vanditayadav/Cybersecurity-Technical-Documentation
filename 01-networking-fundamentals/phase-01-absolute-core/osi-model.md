# OSI Model

## Overview

The Open Systems Interconnection (OSI) model is a seven-layer conceptual framework used to understand how data moves between devices over a network.

It separates network communication into different layers, each responsible for specific functions.

## The Seven Layers

| Layer | Name | Main Function |
|---|---|---|
| 7 | Application | Provides network services to applications |
| 6 | Presentation | Handles data formatting, encryption and compression |
| 5 | Session | Establishes, manages and terminates communication sessions |
| 4 | Transport | Provides end-to-end data transport |
| 3 | Network | Handles logical addressing and routing |
| 2 | Data Link | Handles frames, MAC addressing and local delivery |
| 1 | Physical | Transmits raw bits through physical media |

## Layer Responsibilities

- **Application:** Network services used by applications.
- **Presentation:** Data representation and transformation.
- **Session:** Communication session management.
- **Transport:** Segmentation, ports and transport protocols such as TCP and UDP.
- **Network:** IP addressing and packet routing.
- **Data Link:** Ethernet frames, MAC addresses and local network delivery.
- **Physical:** Cables, connectors, electrical and radio signals.

## Data Encapsulation

As data travels down the OSI layers at the sending device, each layer adds relevant information.

| Layer | Common Protocol Data Unit (PDU) |
|---|---|
| Application–Session | Data |
| Transport | Segment (TCP) / Datagram (UDP) |
| Network | Packet |
| Data Link | Frame |
| Physical | Bits |

At the receiving device, the process is reversed through decapsulation.

## Why the OSI Model Matters

- Helps understand network communication.
- Provides a structured way to troubleshoot connectivity problems.
- Explains how different networking technologies interact.
- Helps identify where a network problem may occur.

## Cybersecurity Relevance

Understanding the OSI model helps classify network activity and security controls by layer, making it useful when analysing network traffic, investigating connectivity issues and understanding network attacks.

---

*This document records the OSI model as part of my foundational networking studies.*
