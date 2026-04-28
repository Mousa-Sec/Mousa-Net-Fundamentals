# Day 8: Advanced Routing Implementations (N10-009)
*Fact-Checked against Professor Messer N10-009 Objective 2.1 & Exam Traps*

## 1. Static vs. Dynamic Routing
### Static Routing
* **Manual Entry:** The administrator manually enters every route[cite: 234].
* **Use Case:** Ideal for **Stub Networks** (remote sites with one path) and high-security needs.
* **Pros/Cons:** Zero overhead (no CPU/RAM used), but no automatic failover and difficult to scale.

### Dynamic Routing
* **Automated Discovery:** Routers use multicasts to find paths and update neighbors.
* **Interior (IGP):** Used *within* an Autonomous System (AS). Examples: OSPF, EIGRP, RIP, IS-IS[cite: 684, 692].
* **Exterior (EGP):** Used *between* different ASs (The Internet). Primary example: **BGP**.

## 2. Protocol Classifications & Metrics
| Type | Logic | Protocol Examples | Metric Used |
| :--- | :--- | :--- | :--- |
| **Distance-Vector** | "Routing by Rumor"; knows neighbors only. | RIP | Hops [cite: 247] |
| **Link-State** | Map-based; maintains a complete topology map. | **OSPF, IS-IS** [cite: 238, 730] | Cost (Bandwidth) [cite: 247] |
| **Path-Vector** | Itinerary-based; tracks Autonomous System paths. | **BGP**  | AS Path length |
| **Hybrid** | Combines distance-vector simplicity with link-state speed. | **EIGRP**  | Complex (Bandwidth/Delay) |

## 3. The Routing Table Decision Process
When a router receives a packet, it follows this strict "tie-breaking" hierarchy:

1. **Longest Prefix Match:** The most specific mask wins (e.g., /32 beats /24).
2. **Administrative Distance (AD):** The "Trustworthiness" score. **LOWER IS BETTER**.
   * Connected: 0
   * Static: 1
   * EIGRP: 90
   * OSPF: 110
   * RIP: 120
3. **Metrics:** Only used to break a tie between routes from the *same* protocol (e.g., lower OSPF Cost).

## 4. Redundancy & Virtualization
### FHRP (First Hop Redundancy Protocol)
* **Purpose:** Provides a **Virtual IP (VIP)** and MAC shared by multiple routers to ensure the default gateway never goes down.
* **Function:** Provides **Automatic Failover** from an "Active" router to a "Standby" router.
* **Implementations:** HSRP (Cisco) and VRRP (Open Standard).

### Subinterfaces
* **Definition:** Logical divisions of a single physical interface (e.g., G0/1.10)[cite: 244].
* **Function:** Allows multiple IP addresses (one per VLAN) on one physical port.
* **Use Case:** **Router on a Stick**—routing between multiple VLANs over a single trunk link.
