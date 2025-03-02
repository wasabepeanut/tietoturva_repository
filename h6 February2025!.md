# One-Way Functions
- A core element of public-key cryptography. 
- Are difficult to reverse, compared to how they are determined.
- Example from the book shortened: It is easy to break a plate, but not as easy to put the broken    pieces together.
- Technically, one-way functions might not be real, but many functions seem that way. E.g. Fixing
  a broken plate might not be impossible, but is really difficult.
- Trapdoor one-way function: one-way function that makes the difficult part achievable with secret
  information. (Schneier 3.2015)

# One-Way Hash Functions
- A core element in modern cryptography.
- In short, converts a input string (**pre-image**) into an fixed-length output string (**hash    value**).
- Collision-free: Two  pre-images can not be determined with the same hash value.
- Message authentication code (MAC): One-way function with a secret key. Hash value can be     
  verified only by one with the key. (Schneier 3.2015)
  


# References
Schneier, B. 3.2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Chapter 2.3: One-Way Functions. O'reilly Media. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003. Accessed: 2.3.2025.

Schneier, B. 3.2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Chapter 2.4: One-Way Hash Functions. O'reilly Media. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec004. Accessed: 2.3.2025.
