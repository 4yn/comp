2023-09-01T09:30Z
[Github](https://github.com/DownUnderCTF/Challenges_2023_Public/tree/main/crypto/apbq-rsa-i)
## abpq rsa i
126 solves, by joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/tree/main/crypto/apbq-rsa-i)
Q: RSA with leaked $h_1, h_2$ where $h_i = a_i \cdot p + b_i \cdot q$ for some random $a_i < 2^{12}$ and $b_i <2^{312}$. #rsa/leak
A: Brute force for all possible $a_1$ and $a_2$ until $\gcd(h_1 \cdot a_2 - h_2 \cdot a_1, n)$ reveals $q$. #math

## abpq rsa ii
26 solves, by joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/tree/main/crypto/apbq-rsa-ii)
Q: RSA with leaked $h_1, h_2, h_3$ where $h_i = a_i \cdot p + b_i \cdot q$ for some random $a_i < 2^{312}$ and $b_i <2^{312}$. #rsa/leak
A:  Use lattice to find an orthogonal vector to $(a_1, a_2, a_3)$. #math #lattice

## hhhhh
14 solves, by hashkitten
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/blob/main/crypto/hhhhh)
Q: Handout is an obfuscated python source file involving md5 hash. #rev 
A: Custom hash xors all md5 hashes of all substrings of the input that include the first character. Generate md5 collision bytestrings in a "nesting-doll" manner and assemble them piecewise, then solve for which pieces will collide with some fixed digest. #hash/collision 

## fnv
27 solves, by hashkitten and joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/blob/main/crypto/fnv)
Q: Find some message where the FNV hash equals to `0x1337133713371337`.
A: Meet in the middle brute force or use z3. #brute-force #z3

## handshake
4 solves, by joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/blob/main/crypto/handshake)
Q: Impersonate admin in a custom handshake protocol involving ECC and nonces. #handshake
A: Use SHA256 hash extension to predict secret intermediates #hash/length-extension

## dilithium±
0 solves, by joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/blob/main/crypto/dilithium)
Q: ?
A: ?

## encrypted mail
3 solves, by joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/blob/main/crypto/encrypted-mail)
Q: Server implements a mailbox system with login (DDH), message signature (DSA) and message encryption systems (LFSR). Forge a message from the admin user to the flag sharer bot to leak the flag. #code-review 
A: DDH challenges use PRNG and decays into LFSR. Message signature signs the ciphertext but not key. Message encryption can be undone with enough known xorpad by solving for initial LFSR state. #prng/mt #lfsr

## lcg card gimmicks
11 solves, by joseph
[Archive](https://github.com/DownUnderCTF/Challenges_2023_Public/blob/main/crypto/lcg-card-gimmicks)
Q: LCG PRNG is used to "draw" cards from a deck, find some seed that generates the same hand. #prng/lcg
A: Use a lattice to solve for consecutive LCG states with multiple modular constraints. #lattice