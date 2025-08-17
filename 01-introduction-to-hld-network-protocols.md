# Lecture 01: Introduction to HLD | Network Protocols

---

## System Design Overview
System Design can be broadly divided into two parts:
- **HLD (High-Level Design)**
- **LLD (Low-Level Design)**

---

## High-Level Design (HLD)
HLD focuses on **architecture and overall system structure**.  
Think of it as *building a home*:
- Cement  
- Bricks  
- Floor  
- Internal Architecture  

### Key Aspects
- **Application**: Deciding the **Tech Stack** (MERN, Spring Boot, Django, etc.)  
- **Cost Optimization**  
- **Database Choices**: SQL, NoSQL, GraphQL, Column-oriented, etc.  
- **Scale estimation**: Thousands → Millions of users (*back-of-the-envelope estimates*)  

---

## Low-Level Design (LLD)
LLD focuses on the **implementation details** and actual coding.  

### Key Aspects
- **Coding part** → OOPS, Design Principles  
- **Design Patterns**  
- **Clean Code** practices  
- **Loosely Coupled Code**  

---

## Quick Comparison: HLD vs LLD

| Aspect             | HLD (High-Level Design)              | LLD (Low-Level Design)             |
|--------------------|---------------------------------------|-------------------------------------|
| Focus              | Architecture & System Structure       | Coding & Implementation Details     |
| Example            | Home building (cement, bricks, floor) | Writing design patterns, OOPS code  |
| Key Decisions      | Tech Stack, Databases, Cost           | Code structure, clean code, coupling|
| Scale              | Handles thousands → millions of users | Focused on efficient coding         |

---

## Request–Response Model

The **Request–Response Model** is the foundation of client-server communication.

### Flow
1. **Client** (Web Browser / Mobile App) sends a **request** to the server over HTTP/HTTPS.  
2. **Server** receives the request and performs **processing**.  
3. Server sends back a **response** to the client.  

### Key Points
- Protocol: **HTTP / HTTPS**  
- Example Hardware: **Server with 32 GB RAM**  
- Follows **Client–Server Model**  
- Used in **Distributed Systems**  
- Can handle **1000+ concurrent users**  

---

## Scaling in System Design

### 1. Vertical Scaling (Scaling Up)
- Add more power (CPU, RAM, Storage) to a **single server**.  
- Example: Upgrading from 16 GB → 64 GB RAM.  
- **Pros**: Simple to implement.  
- **Cons**: Expensive, hardware limits, single point of failure.  

### 2. Horizontal Scaling (Scaling Out)
- Add **more servers/machines** to handle traffic.  
- Example: Moving from **1 server → 10 servers**.  
- **Pros**: Better fault tolerance, cost-effective at scale, high availability.  
- **Cons**: Complex load balancing, data consistency challenges.  

---

## OSI Model (7 Layers of Networking)

The **OSI Model** (Open Systems Interconnection) describes how data flows across networks.

### Layers (Top to Bottom)

1. **Application Layer**  
   - End-user interaction.  
   - Examples: HTTP, HTTPS, FTP, SMTP.  

2. **Presentation Layer**  
   - Data translation, encryption, compression.  
   - Example: SSL/TLS.  

3. **Session Layer**  
   - Manages sessions (start, maintain, terminate).  
   - Example: API session handling.  

4. **Transport Layer**  
   - Reliable data transfer, error correction.  
   - Protocols: TCP, UDP.  

5. **Network Layer**  
   - Routing, addressing (IP addresses).  
   - Protocols: IP, ICMP.  

6. **Data Link Layer**  
   - Error detection, MAC addressing.  
   - Protocols: Ethernet, Wi-Fi.  

7. **Physical Layer**  
   - Actual hardware transmission (cables, signals).  
   - Example: Fiber optics, NIC.  

---

## TCP vs UDP

### Transmission Control Protocol (TCP)
- **Type**: Reliable (but slower)  
- **How it works**:  
  - Data is broken into **packets (p1, p2, p3, …)**.  
  - Each packet is acknowledged (**ACK**) by the server.  
  - If an ACK is not received, the packet is re-sent.  
- **Guarantees**: Delivery, Ordered Packets, Error-checking.  
- **Use cases**: Web Browsing (HTTP/HTTPS), Email (SMTP), File Transfer (FTP).  

---

### User Datagram Protocol (UDP)
- **Type**: Non-Reliable (but faster)  
- **How it works**:  
  - Client sends packets (p1, p2, …) without waiting for ACK.  
  - No guarantee of delivery or order.  
- **Guarantees**: None → Faster, lightweight, low overhead.  
- **Use cases**: Video streaming, Online gaming, Voice calls (VoIP).  

---

### Quick Comparison: TCP vs UDP

| Feature             | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
|---------------------|--------------------------------------|-------------------------------|
| Reliability         | Reliable (ACK for every packet)      | Not reliable                  |
| Speed               | Slower                               | Faster                        |
| Packet Ordering     | Guaranteed                           | Not guaranteed                |
| Error Handling      | Yes                                  | No                            |
| Overhead            | High                                 | Low                           |
| Use Cases           | HTTP, HTTPS, FTP, SMTP               | Gaming, Streaming, VoIP       |

---

## DNS and Internet Protocol (IP)

### Domain Name System (DNS)
- DNS is like the **phonebook of the internet**.  
- Converts **human-readable domain names** (e.g., `google.com`) into **IP addresses** (e.g., `142.250.190.14`).  
- Without DNS, we would need to remember numeric IPs to access websites.  

### Flow of Communication
1. **Client** (Web Browser `B` or Mobile App `M`) initiates a request.  
2. The request first goes to **DNS**, which resolves the domain name into an **IP address**.  
3. Once the IP is found, the client communicates with the correct **Server (S1, S2, …)** using that IP.  

### Internet Protocol (IP)
- **IP (Internet Protocol)** defines the addressing mechanism for devices on the network.  
- Works at the **Network Layer** in the OSI model.  
- Provides a unique address to each device in the network.  

### Key Points
- DNS translates names → IP addresses.  
- IP ensures the request reaches the **correct server (S1, S2)**.  
- Together, DNS + IP enable smooth communication between client and server.  

---

## Final Summary of Lecture 01
- **HLD** = Architecture, scaling, databases, overall system structure.  
- **LLD** = Detailed coding, OOPS, design patterns.  
- **Scaling** = Vertical (scale up) or Horizontal (scale out).  
- **OSI Model** = 7 layers explain network communication.  
- **TCP vs UDP** = Reliability vs Speed trade-off.  
- **DNS + IP** = Enable domain resolution and data routing across the internet.  
