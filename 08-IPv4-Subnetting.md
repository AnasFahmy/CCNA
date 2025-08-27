# IPv4 Classes & Subnetting

- Class A: 0–127, mask 255.255.255.0 **(for /24)** is typical for LANs; *classful A default* is 255.0.0.0
- Class B: 128–191, default mask 255.255.0.0
- Class C: 192–223, default mask 255.255.255.0
- Class D: 224–239 multicast
- Class E: 240–255 research

Formulas:
- Subnets = 2^n  (n = borrowed bits)
- Hosts per subnet = 2^h − 2 (h = host bits)

Quick masks:
- /25 255.255.255.128
- /26 255.255.255.192
- /27 255.255.255.224
- /28 255.255.255.240
- /29 255.255.255.248
- /30 255.255.255.252 (ptp)