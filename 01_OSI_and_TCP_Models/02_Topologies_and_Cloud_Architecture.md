# Day 2: Enterprise Topologies & Cloud Concepts (N10-009)

## Network Architecture Types
* **Star Topology:** All nodes connect to a central device (switch). Single point of failure at the center.
* **Mesh Topology:** All nodes connect to each other. High fault tolerance, high cost.
* **SD-WAN:** Software-Defined WAN. Dynamically routes traffic across multiple connection types (Internet, MPLS, 4G/5G) based on real-time performance.

## Cloud Networking (VPCs)
A **Virtual Private Cloud (VPC)** allows an enterprise to create a private, logically isolated network segment within a public cloud provider (like AWS or Azure). It uses the exact same subnetting and routing rules as a physical network.

## Software-Defined Networking (SDN) & IaC
Modern networks separate the decision-making from the actual data forwarding.
* **Control Plane:** The "brains." The centralized software controller making the routing decisions.
* **Data Plane:** The "muscle." The physical switches and routers executing the controller's instructions.

**Infrastructure as Code (IaC):** Replacing manual hardware configuration with code (e.g., Python, Terraform). This allows an entire network infrastructure to be deployed, modified, or destroyed via a single automated script.

## The Attack Surface
* **Targeting the Control Plane:** If the central SDN controller is compromised, the attacker dictates traffic flow for the entire network.
* **IaC Vulnerabilities:** A single typo in an automation script can deploy hundreds of misconfigured, vulnerable cloud firewalls simultaneously.

## Advanced Cloud Concepts (Exam Compass Patch)
* **SaaS:** Software for end-users (e.g., Office 365).
* **PaaS:** Platforms for developers to build apps.
* **Multitenancy:** Multiple customers sharing one software instance securely.
* **NSG (Network Security Group):** A firewall applied to a specific Virtual NIC (highly granular).
* **NSL / NACL (Network Security List):** A firewall applied to an entire Subnet (less granular).
* **Internet Gateway:** Allows 2-way internet traffic for cloud instances.
* **NAT Gateway:** Allows outbound internet access but restricts unsolicited inbound traffic.
* **Direct Connect:** A dedicated, private physical connection to a cloud provider (bypasses the public internet).
