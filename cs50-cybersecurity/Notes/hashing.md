# Securing Data
---
# Hashing
- Hashing is a method by which a plaintext is converted to a hashed format for data security.
- A hash function creates a hash value, and this value is used to hash the password.
- Whenever the user tries to enter his login credentials, the system pass the inputted password through the hash function and compare the stored password hash value.
- Hypotetically the attacker can use a rainbow table (a table containing all of the stored hash values) but is not practical since it would take TBs, or even PBs of storage for the table only.  
## One Way Hashing
- One-way hash functions are written in code and take in a string of arbitrary length and output a hash of a fixed length.
- Utilizing such a function, the holder of the hash value and hash function will never know the original password.
## Salting
- Its a process by which a additional `salt` is introduced to the hash.
- This ensures that even if 2 password are identical, due to the salt the hash corresponding to both would be different.

