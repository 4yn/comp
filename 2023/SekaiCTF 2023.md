2023-08-25T16:00Z
[Github](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main), [postgame CTFd](https://2023.ctf.sekai.team/)
## cryptoGRAPHy-1
76 solves, by sahuang
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main/crypto/cryptography-1)
Q: Server implements a novel graph encryption scheme, recover graph node IDs from an encrypted path to claim the flag. #code-review
A: Symmetric key is given to the player, just decrypt with the given library. #implement

## cryptoGRAPHy-2
55 solves, by sahuang
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main/crypto/cryptography-2)
Q: Query for an encrypted shortest path on a graph, then prove knowledge of the graph structure. #code-review
A: Chunks of encrypted path map 1:1  to node IDs, reconstruct the graph with encrypted node IDs instead. #implement

## cryptoGRAPHy-3
31 solves, by sahuang
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main/crypto/cryptography-3)
Q: Get all encrypted shortest paths in some tree, goal is to decrypt all encrypted node IDs to original node IDs. #code-review 
A: Root trees using heuristics / subtree hashing to identify isomorphism between encrypted node IDs and original node IDs. #implement 

## Diffecientwo
13 solves, by deut-erium
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main/crypto/randsubware)
Q: Server implements bloom filter using murmurhash3 and 64 seeds per input, user can insert 22 items and needs to forge the existence of a fixed magic string. #hash/collision 
A: Implement the hash in z3 to find plaintexts which collide with at least 3 outputs of the magic string. #z3

## Noisy CRC
49 solves, by Utaha
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main/crypto/noisy-crc)
Q: Query with unique modulus to get the CRC-16 of some secret that is mixed in with 2 other random values. #crc
A: Query with composite modulus $f_i(x) \cdot g(x)$ with fixed $g(x)$, all true CRCs should be the same moduluo $g(x)$. #polynomial #math 

## Noisier CRC
8 solves, by Utaha
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/blob/main/crypto/noisier-crc)
Q: Same as Noisy CRC, but now with check to ensure irreducible modulus, 133 query limit and 12 other random values. #crc
A: "Symbolically" CRT all polynomials together, then use constraints of the secret's coefficients and combinatoric linearization to solve for the true CRCs using linear equations. #polynomial #crt #math/linearization

## RandSubWare
6 solves, by deut-erium
[Archive](https://github.com/project-sekai-ctf/sekaictf-2023/tree/main/crypto/randsubware)
Q: Encryption oracle of toy SPN cipher with 5 rounds and random S-box, recover the key. #block-cipher
A: Low round count is vulnerable to differential or square attack.
