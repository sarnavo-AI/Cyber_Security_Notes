
## Shannon Entropy

	Used in compression, crytography
	Used to determine how random, a given sample of data is

Inference:
	High entropy --> More random
	Low entropy  --> Less random


In absence of that, computers focus on collecting small amounts of **entropy**. This usually means **monitoring keystrokes and mouse movements and the interaction with various peripheral devices, such as hard disks.**

## TRNG

Entropy collected in this way is a type of **true random number generator (TRNG)**, but the approach is not reliable enough to use directly. 
For example, you might need to generate a 4,096-bit key, but the system might have only a couple of hundreds of bits of entropy available. If there are no reliable external events to collect enough entropy, the system might stall.

## PRNG
For this reason, in practice we rely on **pseudorandom number generators (PRNGs)**, which use small amounts of true random data to get them going. This process is known as seeding. 

	Seed is a init value for PRNG, but for the same seed, it gives same output!

From the seed, PRNGs produce unlimited amounts of pseudorandom data on demand. General-purpose PRNGs are often used in programming, but they are not appropriate for cryptography, even if their output is statistically random. Cryptographically secure pseudorandom number generators (CSPRNGs) are PRNGs that are also unpredictable. This attribute is crucial for security; an adversary mustn’t be able to reverse-engineer the internal state of a CSPRNG by observing its output


## /dev/random and /dev/urandom

These are [[character device files]]

A **character device**:
- Sends/receives data **as a stream of bytes**    
- No seeking (`lseek()` doesn’t make sense)
- Typically used for **real-time devices**
    
Examples:
- `/dev/tty`
- `/dev/null`
- `/dev/random`
- Serial ports


In linux, the kernal stores the entropy or random seeds in these files, 
	/random --> blocking (it will wait till we don't get enough entropy)
	/urandom --> non blocking (it will use PRNG)

Actual flow
	TRNG (/random) → seeds → CSPRNG → generates random bytes
