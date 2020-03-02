---
layout: post
title: 'Introduction to encryption'
---

In this article, we will explore the 3 main types of encryption and then look at some examples of them. The concepts will underpin everything you do online, so it’s vital we understand them. 

The first, and oldest, form of cryptography is symmetric cryptography. In this, only one key is used. This means you need to know the same secret that was used to encrypt the message in order to decipher it.  

![Symmetric encryption](/assets/symmetric.png)

There are many examples of symmetric algorithms, from the early Caesar ciphers to the modern-day AES algorithm. AES is used widely today, including being used by the US government. We will now introduce a cryptographer’s best friend, [CyberChef](https://gchq.github.io/CyberChef/). This is a versatile web tool which can be used to do a vast number of cryptography activities. You can make ‘recipes’ of cryptography algorithms which you can put values into. Now to try encrypting something using AES.  

![CyberChef example](/assets/cyberchef_aes.png)

Here you can see that we have successfully encrypted a message, and now it looks nothing like what it did originally. To explain some of the options; they key is the secret that is needed to decrypt the message, the IV (Initialisation Vector) randomizes the output so you can use the same key and message but with different outputs. Then AES has different modes which encrypt the message in different ways, which I’d recommend researching if you are interested. 

The next type of encryption is asymmetric encryption. This instead involves two keys, one used to encrypt a message and one to decrypt it

![Asymmetric encryption](/assets/asymmetric.png)

This is sometimes called public key cryptography. So, say Alice wants to send Bob a message that no one else can read. If we used symmetric cryptography, they’d have to find a way to share the key without anyone seeing it which is rather challenging. Asymmetric encryption fixes this key exchange issues. So, everyone has a ‘keypair’, a public key and a private key. These keys are related so if one is used to encrypt something, the other can decrypt it. So, in our scenario. Bob posts his public keys publicly. Therefore, anyone can encrypt a message with Bob’s public key. But the important thing is that only Bob has the private key, so only he can read these messages. And that’s asymmetric cryptography in a nutshell! A common example of this sort of cryptography is RSA. This algorithm is used widely today, and whilst I won’t discuss the details here, I’d highly suggest reading up on it [here](https://simple.wikipedia.org/wiki/RSA_algorithm).  

The 3rd type is hashing. However, I may have told a lie, as hashing isn’t exactly encryption. Encryption is a two-way thing. If you encrypt something, given the correct information (ie the key), you can decrypt it again. Hashing is a one-way function. You give this function an input, and it returns a fixed length output. Hashing has two common uses: verifying file integrity and protecting passwords. As a hash changes depending on the input, you can use this to compare two files and see if they are the same or not. Then they can protect passwords as they cannot be reversed, so when you enter a password, your input is hashed and compared to the existing hash. 

The final thing to talk about is how to ‘break’ an encryption algorithm. One of the most important things is Kerchoff’s principle. It states that any secure algorithm must be open to be viewed by all others. The reasoning is that any algorithm that relies on secrecy is flawed as it’s very possible someone will get hold of it. But if it remains secure even after people have audited it, it must be secure. To backtrack, secure just means that you can’t get the plaintext from the ciphertext. But when the algorithm is secure, it doesn’t mean you can relax. Attackers can use “side channel attacks”. So instead of attacking the algorithm, you attack how it’s implemented. This often attacks hardware implementations which inadvertently leak information.  

Hopefully you’ve learnt something from this! This was a quick tour but I would highly recommend researching anything here that sounds interesting in more depth. 

 
