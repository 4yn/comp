2023-09-08T14:00Z
## Share
47 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/tree/master/HITCON%20CTF%202023/Share)
Q: SSS where you repeatedly query with $p$ and $n$ and you only get $n-1$ shares. #sss
A: Coefficient generation has an off-by one. Try possible shares of form $(0, g)$ until no coefficients are $p-1$. #codebug

## EZRSA
11 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/tree/master/HITCON%20CTF%202023/EZRSA)
Q: RSA/ECC hybrid based on [paper](https://eprint.iacr.org/2023/1299), you get encryption / decryption oracle and must leak parameters. #ecc #paper
A: Recover $n$ with math, use singular curve to recover $d$, use wiener/boneh-durfee like attack to recover $e$, then factor $n$. #math #ecc/singular

## Echo
20 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/tree/master/HITCON%20CTF%202023/Echo)
Q: Oracle to RSA sign any command in the format `echo {user input}` without padding, goal is to sign a command to execute `./give me flag please`. #rsa/oracle
A: Craft signatures such that `a*b=c*d` to recover $n$ with GCD (either manually or by brute forcing for smooth commands and using lattice to solve for equal product), then use lattice to generate a message that is $0 \bmod n$. #lattice

> `mat.BKZ(block_size=25)` worked within 30s time limit for generating the final message. LLL fails to generate a "short enough" vector when the dimensions are too large.

## Random Shuffling Algorithm
12 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/tree/master/HITCON%20CTF%202023/Random%20Shuffling%20Algorithm)
Q: Recover four 1016-bit $m_i$ when given $ct_{i,j} = (a_{i, j} \cdot m_{i, j} + b_{i, j})^{11} \bmod n_j$ across 100 $n_j$, but the $ct_{i,j}$ are shuffled across $i$. #rsa
A: [Multicast Hastad's](https://fortenf.org/e/ctfs/crypto/2017/04/23/plaidctf-2017-multicast.html) by combining $\prod \left[(a_{i, j} \cdot x + b_{i, j})^{11} - ct_{i, j} \right] \bmod n_j$  using CRT, then solve coppersmith small roots in a 44-degree polynomial in 102400-bit modulus using [**flatter**](https://github.com/keeganryan/flatter). #lattice/coppersmith

> Precompiled flatter available at [1](https://github.com/TheBlueFlame121/Docker-setups) [2](https://hub.docker.com/r/4ync/flatter)

## Collision
11 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/tree/master/HITCON%20CTF%202023/Collision)
Q: Server seeds python `hash()` with unknown 32 bit number. With a known salt, generate a collision. #hash/collision  #code-review
A: Brute force for 24 bits of seed (top 8 have no effect), then use cycle finding (pollard lambda?) to find a collision. #cycle-finding

## Careless Padding
30 solves, by bronson113
[Archive](https://github.com/bronson113/My_CTF_Challenges/tree/main/HITCON%20CTF%202023/Careless%20Padding), [Author wp](https://bronson113.github.io/2023/09/08/hitconctf-2023-careless-padding.html)
Q: Custom padding scheme that checks padding character with second last block contents stacked on an AES-CBC decryption padding oracle. #aes/padding-oracle
A: Intended is to use 1 block of known plaintext to force unpad to cross blocks, (popular) unintended is to abuse python negative indexing.