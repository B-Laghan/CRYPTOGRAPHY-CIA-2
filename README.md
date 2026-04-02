# CRYPTOGRAPHY-CIA-2

Implementation of Route Cipher using PXR Hash Function

Route Cipher
The Route Cipher is a transposition cipher where the message is written into a grid and then read out following a specific "route." In this implementation, the route is a "clockwise inward spiral". 

Custom PXR Hash
This is a non-cryptographic 32-bit hash function designed for high performance and integrity checking.
- XOR Mixing : Ingests character data and position indices.
- Prime Multiplier: Uses the FNV prime `16777619` for bit distribution.
- Circular Rotation: Employs bitwise rotation `(h << 13 | h >> 19)` to ensure bits "wrap around" rather than being discarded, maximizing the avalanche effect.

WORKED EXAMPLE

Plaintext  -  HELLOWORLDPXR 

Hash - C4D2A1B8

Combined - HELLOWORLDC4D2A1B8

Grid (R * C) = 5 * 4

Route Path - Spiral (Clockwise, Inward)

Final Ciphertext - HELL8B1A2D4CROWOLLDX


Hash Function Explanation

FNV Basis: It uses the constants from the Fowler–Noll–Vo hash to provide a solid foundation for non-cryptographic hashing.

Position Sensitivity: By adding the index i during the XOR step, the hash treats "binary" and "brainy" as completely different inputs, even though they contain the same characters.

Bitwise Rotation: The (h << 13) | (h >> 19) operation prevents "clumping" of data and ensures that the internal state is thoroughly mixed with every character.

Finalizer: The constants used in the finalization step (0x85ebca6b) are borrowed from the MurmurHash3 mixer, which helps pass statistical tests for randomness.

