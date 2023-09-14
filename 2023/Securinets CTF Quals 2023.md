2023-08-05T18:00Z
[Github](https://github.com/securinets-insat/Securinets-Quals-CTF-2023-Public)
## DigestiveV2
[Archive](https://github.com/securinets-insat/Securinets-Quals-CTF-2023-Public/blob/main/Crypto/DigestiveV2)
Q: ECDSA signature oracle signs non-admin tokens.
A: Token hashing uses integer representation of token, so sign some non-admin token and use a lattice to find another username where the admin token will have same hash. #lattice 

## Farfour_Post_Quantom
[Archive](https://github.com/securinets-insat/Securinets-Quals-CTF-2023-Public/blob/main/Crypto/Farfour_Post_Quantom)
Q: Working in $\mathbb{F}_{257}$, there is fixed secret vector $k$ and each interaction uses a random generator $g$ and matrix $S$. Matrix $P$ is derived by $P_{i, j} = g^{\text{rand()}} \cdot S_{i, j}$. We can query with vector $q$ to get $P \times q$ with values shuffled and also query for $S \times k$. #linear-algebra
A: Reconnect until generator is $-1 \bmod 257$, then $P$ element-wise is $\pm S_{i, j}$, of which only one is in bounds of $S$ generation. Recover the rows (?columns) of $S$ without information of vector order, then use element-wise sums to form linear equations.

## PolyLCG
[Archive](https://github.com/securinets-insat/Securinets-Quals-CTF-2023-Public/blob/main/Crypto/PolyLCG)
Q: Handout outputs one of two LCG states depending on flag bits to encrypt. #prng/lcg 
A: Assume first number is from the "zero" LCG, then simulate the LCG and look for matching outputs. #crib-dragging

## TTSign
[Archive](https://github.com/securinets-insat/Securinets-Quals-CTF-2023-Public/blob/main/Crypto/TTSign)
Q: Server implements a signature scheme involving an RSA signature + RSA key packed into a custom struct, all encrypted with AES-CBC. Forge a signature. #rsa #aes
A: CBC bit flip such that $d=0$, then send a zero signature. #aes/cbc-bit-flip