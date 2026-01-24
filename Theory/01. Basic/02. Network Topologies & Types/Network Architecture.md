# Computer Network Architecture

A **Computer Network Architecture** defines the **structure, design, and communication pattern** of a network.  
It describes **how devices interact, share resources, and manage data exchange** over a network.  
Network architecture is independent of the physical network (LAN, WAN, etc.), but it works on top of the core network types.

> Note: Understanding network architecture is essential for designing efficient and scalable networks.

---

## Total Types of Computer Network Architecture

At the **core level**, there are **2 main types** of network architecture:

1. **Client-Server Architecture**  
2. **Peer-to-Peer (P2P) Architecture**

Advanced architectures like **hybrid or cloud-based systems** are **built using these two fundamental types**.

---

## 1️ Client-Server Architecture

- **Definition:**  
  A centralized network architecture where a **server provides services** and **multiple clients request** resources from it.

- **Key Features:**  
  - Centralized control and management  
  - Easier maintenance and security  
  - Clients depend on server for data and services  
  - Scalability depends on server capacity  

- **Use Cases:**  
  - Web applications (browser → web server)  
  - Email servers  
  - Online banking systems  
  - Enterprise applications

    
---

## 2️ Peer-to-Peer (P2P) Architecture

- **Definition:**  
  A decentralized network architecture where **all devices (peers) communicate directly** and can act as **both client and server**.

- **Key Features:**  
  - Decentralized control (no central server)  
  - High resilience (no single point of failure)  
  - Each peer can share or request resources  
  - Scalability improves as peers increase  

- **Use Cases:**  
  - File sharing (e.g., BitTorrent)  
  - Blockchain networks  
  - Some VoIP applications  
  - Collaborative distributed computing  

---


---

## Key Differences: Client-Server vs P2P

| Feature | Client-Server | Peer-to-Peer |
|---------|---------------|--------------|
| Central Server | Yes | No |
| Control | Centralized | Distributed |
| Dependency | Clients depend on server | Peers are independent |
| Resilience | Lower (server failure = clients affected) | High (no central dependency) |
| Use Cases | Web, Email, Enterprise Apps | File sharing, Blockchain, Decentralized Apps |

---

## Summary

- **Network Architecture** defines **how devices communicate** over a network.  
- **Core-level architectures = 2**:  
  1. Client-Server  
  2. Peer-to-Peer (P2P)  
- **Advanced architectures** are often **built using these two basic models**.  

> **Note:** Core networks (LAN, WAN, MAN, etc.) provide the infrastructure, while architecture determines the **communication pattern** over that infrastructure.
