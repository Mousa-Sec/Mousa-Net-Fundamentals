# Day 8: Advanced Routing Implementations (N10-009)
*Fact-Checked against Professor Messer N10-009 Objective 2.1*

## 1. The Routing Table & Tie-Breaking
Every Layer 3 device (routers, servers, workstations) maintains a routing table. When a router receives a packet, it must decide which interface to send it out of. If there are multiple paths to the same destination, it follows this strict hierarchy:

1. **Longest Prefix Match (Most Specific wins):** The router always prefers the route with the most specific subnet mask.
    * Example: If a packet is going to `192.168.1.6`, a route for `192.168.1.6/32` will beat a route for `192.168.1.0/24`.
2. **Administrative Distance (AD):** If the masks are identical, the router trusts the protocol with the lowest AD (the "trustworthiness" score).
    * **Directly Connected:** 0 (Most Trusted)
    * **Static Route:** 1
    * **EIGRP:** 90
    * **OSPF:** 110
    * **RIP:** 120
3. **Metric:** If the masks and AD are identical (e.g., two OSPF routes), the router uses the internal protocol metric (like **Cost** for OSPF or **Hops** for RIP) to find the best path.

## 2. Dynamic Routing Protocols
* **IGP (Interior Gateway Protocol):** Used *inside* an organization.
    * **OSPF:** Link-state protocol that builds a map of the network. Metric = Cost (Bandwidth).
    * **RIP:** Distance-vector protocol. Metric = Hops (max 15).
* **EGP (Exterior Gateway Protocol):** Used *between* organizations (The Internet).
    * **BGP (Border Gateway Protocol):** The routing protocol of the global internet.

## 3. First Hop Redundancy Protocol (FHRP)
Standard workstations are configured with a single Default Gateway IP. If that physical router fails, the client loses connection. FHRP provides a "Virtual IP" (VIP) shared between two or more physical routers.
* **How it works:** Clients point to the VIP. If the primary router goes offline, the backup router automatically takes control of the VIP.
* **Implementations:** HSRP (Cisco) and VRRP (Open standard).

## 4. Subinterfaces & Router on a Stick
A single physical router interface can be divided into multiple **Subinterfaces** (e.g., `G0/0.10`, `G0/0.20`).
* **Use Case:** Connecting a router to a switch trunk link to route traffic between multiple VLANs using only one physical cable.
