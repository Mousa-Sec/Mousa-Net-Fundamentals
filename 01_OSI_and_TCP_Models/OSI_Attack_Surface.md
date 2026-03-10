# The OSI Model: An Attacker's Perspective

Unlike standard IT definitions, a Purple Team engineer looks at the OSI model as a segmented attack surface. To defend a network, you must know where the exploit lives.

## Layer 2: Data Link (MAC & Switching)
* **The Target:** Switches, MAC addresses, ARP tables.
* **The Attack:** ARP Spoofing/Poisoning, MAC Flooding, VLAN Hopping.
* **The Defense:** Dynamic ARP Inspection (DAI), Port Security.

## Layer 3: Network (IP & Routing)
* **The Target:** Routers, IP addresses, ICMP.
* **The Attack:** IP Spoofing, Ping of Death, Route Injection, Smurf Attacks.
* **The Defense:** Access Control Lists (ACLs), Anti-spoofing filters, IPsec.

## Layer 4: Transport (TCP/UDP & Ports)
* **The Target:** Ports, TCP Three-Way Handshake, Session State.
* **The Attack:** SYN Floods (DoS), Port Scanning (Nmap), TCP Session Hijacking.
* **The Defense:** Stateful Firewalls, SYN Cookies.

## Layer 7: Application (HTTP, DNS, SMB)
* **The Target:** Web servers, Domain Controllers, End-user applications.
* **The Attack:** SQL Injection, Cross-Site Scripting (XSS), DNS Cache Poisoning, SMB Relay.
* **The Defense:** Web Application Firewalls (WAF), DNSSEC, HTTPS/TLS encryption.
