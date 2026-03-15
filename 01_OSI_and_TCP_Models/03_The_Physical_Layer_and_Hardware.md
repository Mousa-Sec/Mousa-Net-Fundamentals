# Day 3: The Physical Layer & Network Hardware (N10-009)
*Exhaustive Video Mapping: Devices, Copper, Fiber, & Connectors*

## 1. Core Networking Devices (Objective 1.2)
* **Hub (Layer 1):** Legacy. Multiports traffic to all devices (half-duplex). Massive security risk for packet sniffing.
* **Bridge (Layer 2):** Legacy. Connects two different physical networks together and filters traffic based on MAC addresses. (Modern switches are essentially multi-port bridges).
* **Switch (Layer 2):** Forwards traffic intelligently using Application-Specific Integrated Circuits (ASICs) based on MAC addresses (full-duplex).
* **Router (Layer 3):** Routes traffic between distinct IP subnets. Makes forwarding decisions based on IP addresses.
* **Multilayer Switch (Layer 3):** A high-speed switch that also possesses the ability to route traffic based on IP addresses.
* **Repeater / Extender (Layer 1):** Receives a weakened signal, regenerates it to full strength, and pushes it further down the line.
* **Wireless Access Point / WAP (Layer 2):** Acts as a bridge between the wired copper network and the wireless (802.11) network.
* **Cable Modem:** Uses DOCSIS over broadband coaxial cables to connect to an ISP.
* **DSL Modem:** Uses standard telephone lines (RJ11) to connect to an ISP.

## 2. Copper Cabling Standards (Objective 1.5)
* **Twisted Pair Categories (Memorize exact speeds/distances):**
  * **Cat 5:** 100 Mbps (Max 100 meters).
  * **Cat 5e:** 1 Gbps (Max 100 meters).
  * **Cat 6:** 10 Gbps (Max 55 meters).
  * **Cat 6a:** 10 Gbps (Max 100 meters).
* **Shielding Types:**
  * **UTP (Unshielded Twisted Pair):** Standard cable, no protection against Electromagnetic Interference (EMI).
  * **STP (Shielded Twisted Pair):** Contains foil shielding to protect against EMI (used in factories/heavy machinery environments).
* **Plenum vs. PVC:**
  * **Plenum-rated:** Fire-retardant cable jacket required when running cables through the drop-ceiling/HVAC return spaces. Does not release toxic fumes when burned.
  * **PVC (Non-Plenum):** Standard, cheap cable jacket. Toxic if burned.

## 3. Optical Fiber Standards (Objective 1.5)
Uses pulses of light. Completely immune to EMI and wiretapping.
* **Single-mode Fiber (SMF):** Uses lasers. Core is extremely thin. Designed for long-distance WAN links (kilometers).
* **Multimode Fiber (MMF):** Uses LEDs. Core is thicker. Light bounces around inside. Designed for short-distance LANs/Data Centers (up to roughly 2 kilometers).

## 4. Physical Connectors & Transceivers (Objective 1.5)
* **Copper Connectors:**
  * **RJ45:** 8-position, 8-contact (8P8C). Standard ethernet.
  * **RJ11:** 6-position, 2-contact (6P2C). Standard analog telephone.
  * **Punchdown Blocks:** 110 Block (used for standard data/ethernet).
* **Fiber Connectors:**
  * **LC (Local Connector):** Small form factor, uses two separate little clips.
  * **ST (Straight Tip):** Push-and-twist bayonet style connector.
  * **SC (Subscriber Connector):** Square, push-pull snap connector.
* **Transceivers (Hot-swappable modules for switches):**
  * **SFP (Small Form-factor Pluggable):** Supports 1 Gbps fiber connections.
  * **SFP+ (Enhanced SFP):** Supports 10 Gbps fiber connections.
  * **QSFP (Quad SFP):** Supports 40 Gbps fiber connections.

## 5. Specialized Network Devices (Objective 1.2)
* **Load Balancer:** Distributes traffic across multiple servers for fault tolerance and performance.
  * *Layer 4 vs Layer 7:* Can route based on TCP ports (L4) or read the actual URL/Application data (L7).
  * *SSL/TLS Offloading:* Handles the heavy CPU math of encryption/decryption so the backend servers don't have to.
* **Proxy Server:** A middleman device that makes requests on behalf of another machine.
  * *Forward Proxy:* Protects internal users. Hides user IPs from the internet and filters outbound URLs (Corporate web filter).
  * *Reverse Proxy:* Protects internal servers. Sits on the internet edge to intercept and scrub inbound traffic before it hits the real web server.
  * *Transparent Proxy:* Intercepts traffic without the client needing to configure anything or knowing it exists.
