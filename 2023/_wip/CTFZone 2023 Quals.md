2023-08-12T09:00Z
## Come on feel the nonce
Q: Golang server generates 608 ECDSA signatures with the same key, find the secret key to decrypt the flag. #ecdsa
A: Outputs of golang `crypto/rand` are linearly related where 0th + 334th output are equal to the 607th outputs. Use related ECDSA nonces to solve for the key. #prng #ecdsa/nonce-reuse

## Right Decision
Q: 7 of 8 SSS shares are given, where the secret is $s = \phi(n)$ for some fixed $n$. Forge the last share such that $2^{s} \bmod n = 0$. #sss
A: Send the share $(0, 0)$.

## SIGINT
Q: Wounded 1024-bit RSA private key. #rsa/wounded-key
A: Recover partial parameters, brute force for $k_p, k_q$, search and prune for low 152 bits and high 324 bits of $p, q$  and use coppersmith to solve the rest. #search-and-prune #lattice/coppersmith 

## Messenger.zone
Q: ?
A: ?

## Wise sage
Q: Query using arbitrary point $(x, y)$ on BN128 and server provides signature oracle $k \cdot (x, y)$, but point exponentiation is decomposed between two points $k_1 \cdot (x, y) + k_2 \cdot (x \cdot \beta, y)$. #ecc
A: Send invalid points and solve the discrete log over different curves. #pohlig-hellman 