# Day 3: The Physical Layer & Network Hardware (N10-009)
*Exhaustive Video Mapping: Devices, Security, Storage, & Cabling*

## 1. Core Infrastructure & Wireless (Objective 1.2)
* **Router (Layer 3):** Routes traffic between different IP subnets across the world.
* **Switch (Layer 2):** Forwards traffic in hardware using ASICs (Application-Specific Integrated Circuits) based on MAC addresses. Can provide Power over Ethernet (PoE).
* **Layer 3 Switch:** A single device containing both Layer 2 switching and Layer 3 routing functionality.
* **Access Point / AP (Layer 2):** Acts exclusively as a bridge translating between the 802.11 wireless network and the 802.3 wired Ethernet network.
* **Wireless LAN Controller (WLC):** A centralized management tool ("single pane of glass") used to configure, update, and monitor dozens of Access Points simultaneously. It manages roaming and access policies. Often proprietary to the AP manufacturer.

## 2. Security & Edge Devices (Objective 1.2)
* **Firewalls:**
  * *Traditional:* Filters traffic strictly by TCP/UDP port numbers.
  * *Next-Generation Firewall (NGFW):* Application-aware filtering. Usually acts as a Layer 3 router, handles Network Address Translation (NAT), and provides encrypted VPN tunnels.
* **IDS vs. IPS:**
  * *IDS (Intrusion Detection System):* Monitors for known exploits (buffer overflows, XSS) and triggers alerts/alarms. Cannot block traffic.
  * *IPS (Intrusion Prevention System):* Sits in the flow of traffic and actively blocks attacks before they enter the network.
* **Proxy Server:** A middleman device that makes requests on the user's behalf to perform URL filtering, caching, and malware scanning.
  * *Explicit Proxy:* Requires configuration on the user's OS or browser.
  * *Transparent Proxy:* Operates invisibly on the network without user configuration.
* **Load Balancer:** Distributes inbound traffic across multiple backend servers to maintain uptime. 
  * *Features:* TCP/SSL Offloading (handling the encryption math), Caching, and Quality of Service (QoS) to prioritize specific traffic.

## 3. Network Storage (Objective 1.2)
* **NAS (Network Attached Storage):** Provides **File-level access**. When modifying a document, the entire file must be pulled across the network to memory, changed, and written entirely back.
* **SAN (Storage Area Network):** Provides **Block-level access**. Functions like a local hard drive. If you change one paragraph in a massive file, it only rewrites those specific modified blocks. Highly efficient, often placed on isolated high-bandwidth networks.

## 4. Cabling & Connectors (Objective 1.5)
* **Copper Categories:** Cat 5e (1 Gbps / 100m), Cat 6 (10 Gbps / 55m), Cat 6a (10 Gbps / 100m).
* **Copper Connectors:** RJ45 (Network), RJ11 (Telephone).
* **Plenum Cable:** Fire-retardant jacket required in HVAC drop-ceilings; does not release toxic fumes.
* **Fiber Optic:** Immune to EMI. 
  * *Single-mode:* Lasers, long-distance WANs.
  * *Multimode:* LEDs, shorter LANs/Data Centers.
* **Fiber Connectors:** LC (clips), ST (bayonet twist), SC (square push-pull).
* **Transceivers:** SFP (1 Gbps), SFP+ (10 Gbps), QSFP (40 Gbps).
