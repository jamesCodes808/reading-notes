# Cryptography

## What is the basic principle behind the Caesar Cipher, and how was it used historically?

The Caesar Cipher is a way to secretly code messages by shifting each letter in the alphabet by a certain number of places. For example, if we shift every letter in the alphabet by 3 places, then A becomes D, B becomes E, and so on. This way, we can write messages that only people who know the secret shift number can understand. This cipher was used a long time ago by Julius Caesar to send secret messages to his army generals.

## What are the key differences between symmetric and asymmetric encryption? How is asymmetric used in secure communication today?

Symmetric encryption uses the same secret key to both encrypt and decrypt information, while asymmetric encryption uses two different keys, a public key and a private key. 

The public key is used to encrypt information, while the private key is used to decrypt it. Asymmetric encryption is used in secure communication today to protect sensitive information such as passwords, credit card numbers, and other private data that needs to be sent over the internet. 

This helps to keep the information safe from hackers and other people who might try to steal it.

## How do computers generate random numbers, and what are the differences between true random number generation (TRNG) and pseudo-random number generation (PRNG)? Discuss their use cases in cryptography.

Computers use special programs called algorithms to generate random numbers. There are two types of random numbers: true random numbers, which are generated by unpredictable physical processes like atmospheric noise or radioactive decay, and pseudo-random numbers, which are generated using mathematical formulas. 

True random numbers are more secure and harder to predict, while pseudo-random numbers are faster to generate but can be predicted if someone knows the formula used. In cryptography, true random numbers are used for highly secure encryption, while pseudo-random numbers are used for less sensitive tasks like generating session keys.

## What’s the difference between encryption and decryption? Explain with an analogy.

Encryption is like putting a secret message in a locked box, where only the person with the key can open it and read the message. Decryption, on the other hand, is like using the key to unlock the box and reveal the secret message inside. 

So, encryption is the process of converting a message into a secret code, while decryption is the process of converting the secret code back into the original message. 

It's like writing a note to your best friend in a secret code that only you two understand, and then decoding it later to read what you wrote.

## Things I want to know more about

- I understand the concept, I would like to put cryptography to practice in my code.

>References
>
>[Encryption, decryption, and cracking](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)
>
>[Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher)
>
>[Introduction to Cryptography](https://thebestvpn.com/cryptography/)
>
>[How Computers Generate Random Numbers](https://www.howtogeek.com/183051/htg-explains-how-computers-generate-random-numbers/)