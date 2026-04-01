# CRYPTOGRAPHY-CIA-2

Implementation of Route Cipher using PXR Hash Function

Route Cipher
The Route Cipher is a transposition cipher where the message is written into a grid and then read out following a specific "route." In this implementation, the route is a "clockwise inward spiral". 

Custom PXR Hash
This is a non-cryptographic 32-bit hash function designed for high performance and integrity checking.
- XOR Mixing : Ingests character data and position indices.
- Prime Multiplier: Uses the FNV prime `16777619` for bit distribution.
- Circular Rotation: Employs bitwise rotation `(h << 13 | h >> 19)` to ensure bits "wrap around" rather than being discarded, maximizing the avalanche effect.

