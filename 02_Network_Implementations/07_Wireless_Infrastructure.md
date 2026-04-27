# Day 7: Wireless Infrastructure & Security (N10-009)
*Fact-Checked against Professor Messer N10-009 Objective 2.4*

## 1. The 802.11 Wireless Standards
You must memorize the frequencies and specific features of these IEEE standards:
* **802.11a:** 5 GHz frequency. Up to 54 Mbps. (Legacy).
* **802.11b:** 2.4 GHz frequency. Up to 11 Mbps. (Legacy).
* **802.11g:** 2.4 GHz frequency. Up to 54 Mbps. (Backwards compatible with 802.11b).
* **802.11n (Wi-Fi 4):** 2.4 GHz and 5 GHz. Introduced **MIMO** (Multiple-Input Multiple-Output) using multiple antennas. Up to 600 Mbps.
* **802.11ac (Wi-Fi 5):** 5 GHz exclusively. Introduced **MU-MIMO** (Multi-User MIMO), allowing the access point to transmit to multiple clients simultaneously. Up to ~7 Gbps.
* **802.11ax (Wi-Fi 6):** 2.4 GHz and 5 GHz. Introduced **OFDMA** (Orthogonal Frequency-Division Multiple Access), drastically improving efficiency in highly congested environments. Up to ~9.6 Gbps.

## 2. Frequencies & Channel Selection
* **2.4 GHz Band:** Travels further and penetrates walls easily, but is highly susceptible to interference from microwaves, Bluetooth, and cordless phones. 
  * *The Rule of 3:* To avoid overlapping interference, you must strictly use **Channels 1, 6, or 11**.
* **5 GHz Band:** Extremely fast and much less crowded, but has higher physical attenuation (it struggles to penetrate physical walls and travels shorter distances). Dozens of non-overlapping channels are available.

## 3. Wireless Encryption Protocols
* **WPA2 (Wi-Fi Protected Access 2):** Uses **AES** (Advanced Encryption Standard) for encryption and **CCMP** for data integrity. Vulnerable to offline dictionary/brute-force attacks if the 4-way handshake is captured.
* **WPA3 (Wi-Fi Protected Access 3):** The modern standard. Replaces PSK with **SAE** (Simultaneous Authentication of Equals), entirely mitigating offline dictionary attacks. Also forces Perfect Forward Secrecy.
* **Authentication Modes:**
  * *Personal (PSK):* Uses a Pre-Shared Key. Everyone types in the exact same Wi-Fi password.
  * *Enterprise (802.1X):* Requires a centralized authentication server (like RADIUS). Users log in to the Wi-Fi using their own unique corporate username and password.

## 4. Antennas
* **Omnidirectional Antennas:** Radiate signal outward in a 360-degree circle. Used for standard office/home APs (e.g., standard dipole).
* **Directional Antennas:** Focus all radio energy in a single, narrow beam. Used for point-to-point bridging between two buildings. Examples include **Yagi** and **Parabolic**.
## 5. Wireless Frequencies & Channels
* **Frequencies:** 802.11 networks commonly use **2.4 GHz, 5 GHz, and 6 GHz** bands.
* **Channels:** Instead of memorizing exact frequencies (e.g., 2.437 GHz), the IEEE groups these into easy-to-use channels (e.g., Channel 6 or Channel 44).
* **Bandwidths:** The amount of frequency used by a channel. Common sizes are **20 MHz, 40 MHz, 80 MHz, and 160 MHz**. 
* **2.4 GHz Spectrum:** Has only **three non-overlapping channels** when using standard 20 MHz bandwidths.
* **Band Steering:** A feature on access points that forces or "steers" a capable client device to the optimal frequency (often the 5 GHz band). Without band steering, a client will simply connect to whatever frequency has the strongest physical signal (usually the crowded 2.4 GHz band), which often results in worse throughput.

## 6. Wireless Interoperability (802.11h & ITU)
The ITU (International Telecommunications Union) provides worldwide guidelines to manage wireless technologies. The **802.11h** standard adds features so different networks can operate in the same geographic area without stepping on each other:
* **DFS (Dynamic Frequency Selection):** The access point automatically scans for existing frequencies in use and selects a channel that will not conflict with neighboring networks. If the environment changes, the AP automatically changes its channel and forces connected clients to move with it.
* **TPC (Transmit Power Control):** Traditionally, client devices (like phones) decided how much radio power to use. TPC puts power control in the hands of the access point. The AP can tell a client to lower its transmit power, reducing interference with third-party networks nearby.

## 7. Wireless Encryption & Cipher Modes
If you are sniffing traffic as a Purple Teamer, you need to know exactly how the packets are secured.
* **WEP (Wired Equivalent Privacy):** The original encryption. Highly vulnerable to cryptographic breaks and quickly replaced.
* **WPA (Wi-Fi Protected Access):** A temporary stopgap replacement designed to run on the exact same legacy hardware as WEP.
* **WPA2:** Introduced in 2004. Uses the **CCMP** block cipher mode (Counter Mode with Cipher Block Chaining Message Authentication Code Protocol). 
  * *Encryption:* Uses **AES** for data confidentiality.
  * *Integrity:* Uses **CBC-MAC** for the message integrity check.
* **WPA3:** Introduced in 2018. Uses the more advanced **GCMP** block cipher mode (Galois/Counter Mode Protocol).
  * *Encryption:* Continues to use **AES** for data confidentiality.
  * *Integrity:* Uses **GMAC** (Galois Message Authentication Code) to verify the data was not tampered with during transit.
