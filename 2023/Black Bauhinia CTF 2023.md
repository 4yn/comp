2023-08-19T00:00Z
[Github](https://github.com/blackb6a/blackb6a-ctf-2023-challenges)
## How to Stop Time
6 solves, by Mystiz
[Archive](https://github.com/blackb6a/blackb6a-ctf-2023-challenges/tree/main/01-how-to-stop-time)
Q: User gives prime $q$, server verifies that $q$ is prime and safe, then user has to solve a discrete log modulo $4 \cdot q - 1$. #prime #discrete-log
A: Prime checking allows any negative number, so send a smooth negative number and solve the discrete log with Pohlig-Hellman. #pohlig-hellman 

## Quantum Entanglement
2 solves, by hoifanrd
[Archive](https://github.com/blackb6a/blackb6a-ctf-2023-challenges/tree/main/02-quantum-flip)
Q: Handout includes a script that generates a xorpad from `Qiskit`, a known plaintext-ciphertext pair of files and encrypted flag. #code-review
A: The xorpad is derived from high bits of `mt19937_64` outputs and decays into a LFSR. Use the known plaintext-ciphertext file to recover random state and decrypt the flag. #prng/mt #lfsr

## grhkm's babyRSA
15 solves, by grhkm
[Archive](https://github.com/blackb6a/blackb6a-ctf-2023-challenges/tree/main/03-grhkm_s-babyrsa)
Q: RSA, but $e\approx N^\frac{1}{12}$ and low 203 bits of $d_p$ and $d_q$ are known. #rsa/leak 
A: Implement [paper](https://eprint.iacr.org/2022/271.pdf), where the main insight is to solve for relations in $e\cdot2^{203}$ instead of $2^{203}$ to improve bounds on coppersmith. Use coppersmith to solve for $k_p$ and $k_q$, then use coppersmith again to solve for $p$ and $q$. #lattice/coppersmith 

## YADE (Yet Another Diophantine Equation)
4 solves, by grhkm
[Archive](https://github.com/blackb6a/blackb6a-ctf-2023-challenges/tree/main/31-YADE)
Q: ?
A: ? #math

## Crypto Chef
1 solve, by hoifanrd
[Archive](https://github.com/blackb6a/blackb6a-ctf-2023-challenges/tree/main/32-crypto-chef)
Q: ?
A: ?
## Amnesia
? solves, by ?
[Archive](https://github.com/blackb6a/blackb6a-ctf-2023-challenges/tree/main/18-amnesia)
Q: Webserver implements JWT auth and expects special user. #web #jwt
A: Guess that the RSA key is in `/.well-known/jwks.json`, then factor the weak RSA key to forge a token. #rsa