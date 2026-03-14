# Day 3: The Physical Layer & Network Hardware (N10-009)

## Cabling & Connectors (Layer 1)
* **Copper (Twisted Pair):** Uses electrical signals. Vulnerable to Electromagnetic Interference (EMI) and physical wiretapping.
  * *Categories:* Cat 5e (1 Gbps), Cat 6 (10 Gbps up to 55m), Cat 6a (10 Gbps up to 100m).
  * *Connectors:* RJ45 (Network), RJ11 (Telephone).
* **Fiber Optic:** Uses pulses of light. Immune to EMI and extremely difficult to covertly tap.
  * *Single-mode:* Uses lasers, designed for long distances (WANs).
  * *Multimode:* Uses LEDs, designed for shorter distances (LANs/Data Centers).

## Core Network Devices
* **Hub (Layer 1):** Legacy device. Multiports traffic to all connected devices. A massive security risk as all traffic can be sniffed by anyone on the hub.
* **Switch (Layer 2):** Forwards traffic intelligently based on MAC addresses.
* **Router (Layer 3):** Routes traffic between completely different networks using IP addresses.

## The Attack Surface
* **Physical Access is Root Access:** If an attacker can plug a rogue device (like a Raspberry Pi) directly into an unsecured wall port, they bypass the perimeter firewall entirely.
* **MAC Flooding:** Attackers can flood a switch's MAC address table, forcing it to fail open and broadcast all traffic, enabling local packet sniffing.
