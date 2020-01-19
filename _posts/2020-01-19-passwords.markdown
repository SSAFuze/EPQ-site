---
layout: post
title: 'How do passwords keep me safe?'
---

Often, it seems like the only thing standing in between your valuable data and a malicious attacker is your password. But how can a small set of characters protect your data? 

 

Well, let's talk about the obvious thing first. Passwords stop people accessing your account unless they know the password. Simple, problem solved. Well, not really. What’s to stop someone just filling the password form with every possible combination? Apart from this being time consuming for an attacker and very noisy, most modern sites use lockout thresholds. So, if you get your password wrong a certain amount of times, you either have to wait a certain amount of time before trying again or you may have to ask an IT person to let you back in. 

 

However, one of the more common methods attackers use is ‘password spraying’. This is where attackers take usernames/email addresses (we don’t normally keep these secret) and try a few common passwords on each of them. In some cases, such as an attacker trying to gain access to a corporate network, all it takes is one employee to use a weak password such as the dreaded ‘password’ and the attacker has access. The lesson here is to always avoid common passwords and choose longer, more complex ones.  

 

Another targeted tactic that attackers may use is leveraging password dumps. It is inevitable that some sites will be compromised, and user's data including passwords may be leaked. Now, competent sites will have encrypted their user’s passwords using a secure hashing algorithm (post about this coming in the future!) such that it’s now useless to an attacker. But like anyone else, sometimes developers cut corners and store passwords in plaintext or used an insecure encryption algorithm. If they’ve done this and a hacker gains access, they probably have your password. You can even see if your password has been found in a password dump before using Have I Been Pwned (https://haveibeenpwned.com/Passwords); this site can also let you search for your email address to see if it has been found. The solution to this is to use different passwords for different accounts. But these may be hard to remember, which we can address later. 

 

Now for a quick taster of what hashing is. It’s a form of cryptography where it's incredibly easy to go one way but impossible go back the other way. So, when you set a password, this password is hashed, and the output is stored. Then when you log in, the password you enter is hashed using the same algorithm – and they are compared. This can cause issues which will be discussed in a later post. 

 

This is probably as a good a time as any to introduce the infamous XKCD comic: 

![Password Strength XKCS](/assets/password_strength.png)

This is true because the only way to ‘crack’ a hashed password is to brute force it. This is achieved either by using a database of common passwords and their hashes or by just simply hashing all possible combinations until you find a match. Every character you add to a password exponentially increases the time required to crack it, which is why long passwords are considered good advice. Another layer of security can be added to hashed passwords by ‘salting’ them, something that will be covered elsewhere. 

 

But one of the best ways to protect an account is to employ a form of two factor authentication. Even if an attacker has your password, if they require a 2FA code sent via text or email, they can't get access to your account.  

 

I hope you’ve learnt something here! Stay tuned for more posts on interesting topics. 

 

Extra resources: 

 

https://random-ize.com/how-long-to-hack-pass/ 

https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt 

Download link for the famous rockyou.txt, commonly used for trying to brute force passwords 

 
