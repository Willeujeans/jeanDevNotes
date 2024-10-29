# Cryptography
_Study of techniques that create secure communication._
## Encryption
_Scrambling data so the only entities with a key can understand it._
## Symmetric Encryption
_The same Key is used for both encrypting and decrypting data._
Both sides need the key to communicate without having their data be decrypted, however if an attacker gets that key they could decrypt all the data.  
This is an efficient approach however, due to only needing one algorithm and key for both sides, the computational power is lessened.  
## Cyphers
### Block Cyphers
_An algorithm that encrypts fix sized blocks of plaintext._
Takes large blocks of text and turns it into the corresponding cipher-text.  
Best approach for storing data that will not be moved, or altered often.  
### Stream Cyphers
_An algorithm that encrypts plaintext bit by bit._
Often used in applications where data flows continuously.  

# Message Authentication Code
_A MAC is a checksum to prove the data received is the data sent._
A cryptographic checksum generated using a secret key, which allows the recipient of the message to verify that the received message has not been altered or tampered with, and that it indeed originated from the expected sender. 