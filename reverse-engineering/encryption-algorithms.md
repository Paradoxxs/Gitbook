# Encryption Algorithms

key indicators for recognising encryption algorithms.

### Symmetric algorithms

#### RC4

**Indicators**

Usage of 0x100 in two loops, first in the initialization stage and then scrambling stage. 1 to 256 bytes in length, it very common that the key have a length of 16 bytes

**Consist of three stages**

* Key-scheduling algorithm (initialization stage)
  * Create substitution box with values from 0x00 to 0xFF
* Pseudo-random generation stage ( scrambling stage)
  * Uses the key to scramble the substitution box, there by creating an stream of semi-random bytes
* XOR stage
  * XOR the input against the cream stream

#### Salsa20

The algorithms can be recognized based on the constant iteraction with two strings.

**pseudocode**

Main component of the algoritm is the Quater-Round with takes 4 word input and produces 4 word output

```
Define QR(a, b, c, d)
( b ^= ROTL(a + d, 7)
c ^= ROTL(b + a, 9)
d ^= ROTL(c + b,13)
a ^= ROTL(d + c,18))
```

#### AES

The easiest way to recognize AES algorithm is the lookup table to either S-Boxes or T-Tables all depending upon the implementation.

#### Blowfish

Can be recognized on the required S-boxes and P-arrays.

### Asymmetric alorithms

#### RSA

It every common for authors to use the WinCrypt API as it simple, reliable and secure

**Math**

```
c = ciphertext
p and q = prime numbers
n = p * q
phi = (p-1)*(q-1)  
d = inverse(e, phi)  
m = pow(c,d,n)
```

**Weakness**

Small e value can be a problem, the same goes for the n value if the n value is small we can figure out what the two prime number that was multiplied together to the result, sites like factordb.com can help with this problem.

#### Elliptic Curve (ECC)

Because of the difficult of writing the algorithm correctly, you are usully be able to find open source respository that was used to implement the algorithm, e.g. [curve25519-donna](https://github.com/agl/curve25519-donna)
