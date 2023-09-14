2023-04-14T21:00Z
## bivalves/scallop
39 solves, by mserrano and ubuntor
Q: LFSR-like cipher encrypts known plaintext with flag at end
A: Solve for seed with z3. #z3

## fastrology/waxing crescent 🌒
30 solves, by ubuntor and strikeskids
Q: Javascript `Math.random()` is used to generate a stream of emoji from 4 choices, predict the next characters to get the flag.
A: Each emoji corresponds to 2 high bits of PRNG output, recover the PRNG state. #prng

## fastrology/new moon 🌑
27 solves, by ubuntor and strikeskids
Q: Javascript `Math.random()` is used to generate a stream of emoji from 13 choices, predict the next characters to get the flag.
A: Each emoji corresponds to a range of possible floats, use the high bits which do not change within each range to recover the PRNG state. #prng

## fastrology/full moon 🌕
25 solves, by ubuntor and strikeskids
Q: Javascript `Math.random()` is used to generate a stream of emoji from 9 choices with added noise, predict the next characters to get the flag.
A: Each emoji corresponds to a range of possible floats which change after some repititions, use the high bits which do not change within each range to recover the PRNG state. #prng

## fastrology/waxing gibbous 🌔
16 solves, by ubuntor and strikeskids
Q: Javascript `Math.random()` is used to generate a stream of emoji from 13 choices, with all instances of the 13th emoji replaced with random noise, predict the next characters to get the flag.
A: Each emoji corresponds to a two disjoint ranges of possible floats, use the high bits which do not change across both ranges to recover the PRNG state. #prng

## The Other CSS/Disk A
11 solves, by bluepichu, foxtrot and ubuntor
Q: Server implements a handshake based on Content Scramble System involving LFSRs and block ciphers, pass the handshake. #block-cipher 
A: Solve for block cipher key using z3 or replay parameters from two server handshakes. #z3 #handshake/replay 

## The Other CSS/Disk B
11 solves, by bluepichu, foxtrot and ubuntor
Q: Using plaintext and ciphertext pairs of some encryption system involving LFSRs and block ciphers, recover a master key. #lfsr
A: Efficiently brute force for LFSR key and chain with solution to disk A to obtain master key.

