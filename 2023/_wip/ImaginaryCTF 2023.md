2023-07-21T19:00
[postgame CTF site](https://2023.imaginaryctf.org/Challenges.html)
## rsa
262 solves, by Eth007
Q: ?
A: ?
## emoticons
152 solves, by Eth007
Q: ?
A: ?

## signer
94 solves, by Eth007
Q: ?
A: ?

## Tan
32 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/blob/master/ImaginaryCTF%202023/Tan)
Q: From $\tan(x)$ with 1024 bits of precision, find the integer $x$. #math
A: $x - k \cdot \pi = \arctan(y)$, so find $\arctan(y)$ to good precision and use lattice to solve for $k$. #lattice 

## Wasteful
31 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/blob/master/ImaginaryCTF%202023/Wasteful)
Q: RSA, but $e < n^{0.5}$ is a random prime and we are given $e + k \cdot \phi(n)$ instead with some large prime $k$. #rsa/leak 
A: ?

## Blind guess
8 solves, by A~Z
Q: In $\mathbb{F}_{13}$, generate 10 by 10 matrix $M$ and 10 element vector $c$, then update $c = M^r \times c$ with PRNG generated $r$. By repeatedly guessing $q$ and being told how many places of $c$ are equal to $M \times q$, predict $c$.
A: Use heuristics to solve for $M$ by eliminating candidates for each element, then use matrix discrete log to recover random state and predict future cards.

## Flagtor
5 solves, by Robin_Jadoul
Q: Handout contains encryption program written in factor language and a text file with numbers. #rev 
A: Encryption program xors flag with a safe random xorpad and leaks matrix-vector products which are derived from xorpad and PRNG. Leak PRNG calls with a side channel, use the flag format and lineraize quadratic combinations of xorpad variables to solve system of equations. #math/linearization 

## elliptic
4 solves, by Eth007 and A~Z
Q: ?
A: ?

## Imaginary Casino
3 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/blob/master/ImaginaryCTF%202023/Imaginary%20Casino)
Q: ?
A: ?

## Sus
3 solves, by maple3142
[Archive + Author wp](https://github.com/maple3142/My-CTF-Challenges/blob/master/ImaginaryCTF%202023/Sus)
Q: RSA modulus of the form $p \cdot (p^2 + p + 1) \cdot r$, where $p^2 + p + 1$ is prime. #rsa
A: Use properties of polynomial quotient rings to factorize a prime of special form. #math