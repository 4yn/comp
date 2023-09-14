2023-07-29T00:00
[Github](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive)
## fizzbuzz100
134 solves, by wwm
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/fizzbuzz100)
Q: Flag is encrypted with RSA and RSA decryption oracle is given, but decrypting the flag is disallowed. #rsa
A: Decrypt $ct \cdot 2^e \bmod n$, then divide the decryption by 2. #rsa/homomorphism

## eyes
75 solves, by emh
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/eyes)
Q: ?
A: Deobfuscate matrix operations into a system of linear equations / using PIE. #math

## cbc
59 solves, by wwm
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/vcbc)
Q: Shift cipher but each block is shifted by both the key and the previous encrypted block.
A: Unshift all blocks with previous block, then use a vigenère cipher solver. #classical-cryptography

## fizzbuzz101
19 solves, by wwm
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/fizzbuzz101)
Q: Flag is encrypted with RSA and RSA decryption oracle is given, but only reveals if decryption is divisible by 3 and 5.
A: Adapt RSA LSB oracle to split possible intervals of $m$ into 3 each time by querying $k \cdot m = 0 \bmod 3$ and $-k \cdot m = 0 \bmod 3$. #rsa/lsb-oracle

## QCG-k
16 solves, by Day
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/qcg-k)
Q: Recover a DSA key using 18 signatures, where nonces are generated with a 15-degree polynomial such that $k_i = f(k_{i-1})$.
A: Each pair of sequential signatures generates a relation $k_i = k_{i-1} \cdot m + c = f(k_{i-1})$. Work symbolically with $k_0$ to obtain several $k_0 \cdot m_a + c_a = f(k_0 + \cdot m_b + c_b)$, find the Lagrange polynomial satisfying these relations and solve for $k_0$ where the coefficient of $x^{16}$ is zero.

## fizzbuzz102
14 solves, by wwm
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/fizzbuzz102)
Q: ?
A: ?

## oil-spill
3 solves, by emh
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/oil-spill)
Q: ? #pqc
A: ?

## superbox
2 solves, by pot
[Archive](https://github.com/Crusaders-of-Rust/corCTF-2023-public-challenge-archive/tree/master/crypto/superbox)
Q: ?
A: ?