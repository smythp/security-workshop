## Encryption

Have you ever used a cipher? Probably the most famous cipher is the Caesar Cipher, in which a message is encoded by moving each letter a fixed position down the alphabet. For example, the message

    Hello, world!
	
would become

    Khoor, zruog!
	
by shifting all letters down the alphabet by 3.

The Caesar Cipher is a way to keep messages secret by leveraging a piece of information known by the message writer and the message receiver, but hopefully not by a third party who might intercept the message. Unfortunately, the Caesar Cipher is simple enough that the code can easily be reverse-engineered.

To prevent reverse engineering, modern encryption procedures use mathematical operations that are easy to perform, but difficult to reverse. The most common form of one-way math is calculating primes—it's easy to come up with a large number by multiplying primes together, but it's difficult and slow to reverse the operation and factor the primes back out.

### A Problem

Historically, ciphers had a problem. Even if you came up with a really great cipher that you thought no one could break, you still needed to get that cipher to your agent without it being intercepted by a third party. If your cipher were to be intercepted, all further communications with that agent would be compromised. In practice, this meant that in-person meetings were needed to decrease the possibility that cipher information was not intercepted in transit.

With the rise of the internet, this problem became a lot more serious. Communication on the internet often needs to be private, but meeting with people in person to agree on an encryption key is almost always impractical. Luckily, this is largely a solved problem, thanks to a clever idea known as public/private key encryption.

### Public/Private Key Encryption

The insight that public/private key encryption is based on is that you can create one key to encrypt information and a separate one to decrypt that information. The encryption key is made public, and is referred to as the "public key." The key for decryption is kept private, and is known as the "private key." To create a secure message, the sender uses a public key to encrypt the message. On the other end, the recipient uses their private key to decrypt it. The power of this system is that it doesn't matter if the public key is intercepted by a third party. In fact, it's better if the public key is widely known. Since the public key can only be used to encrypt, but not to decrypt, a message, it won't help a third party to decrypt an intercepted communication.

For example, imagine that Maria is a journalist. She wants people to be able to send her secure communications if they choose. She creates a public/private key pair using a tool such as GPG. She keeps the private key on her computer and doesn't share it with anyone. The public key she places on her website for anyone to see. Say that Catherine, a whistleblower, wants to send Maria a secure message. She would first use the public key on Maria's website to encrypt it. Once it's been encrypted, even Catherine isn't able to decrypt the message—she doesn't have the private key. Catherine then sends the encrypted message to Maria. Maria uses her private key to decrypt the message and reads it.
