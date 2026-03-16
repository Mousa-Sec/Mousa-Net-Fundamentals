# Day 4: IPv4, IPv6, and Routing Protocols (N10-009)
*Exhaustive Video Mapping: Subnetting Math, IP Standards, and Network Routing*

## 1. Binary Math & Conversions (Objective 1.7 - Transcript Verified)
* **The 8-Bit Octet:** An IPv4 address is made of four 8-bit chunks (octets). An 8-bit chunk contains 8 ones and zeros. 
* **The Conversion Chart:** Based on the powers of 2. Memorize from left to right:
  `128 | 64 | 32 | 16 | 8 | 4 | 2 | 1`
* **Maximum Value:** If an octet is all ones (`11111111`), the mathematical total is exactly **255** (128+64+32+16+8+4+2+1).
* **Binary to Decimal Logic:** Place the binary under the chart. Add the values where a `1` exists. Ignore values where a `0` exists.
* **Decimal to Binary Logic:** Start at 128. If the chart value fits into your target number, place a `1` and subtract. If it doesn't fit, place a `0` and move right.
