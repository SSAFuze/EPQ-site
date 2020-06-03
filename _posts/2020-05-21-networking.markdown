---
layout: post
title: "An Introduction to Networking"
---

In this article, we will be exploring the vitally important field of computer networking. This is a massive field so we couldn’t hope to explore it all here, nonetheless, we will explore some basic ideas in detail, helping you get started to learn more after reading this article. 

Firstly, we need to answer a question which might seem quite simple - what is networking? At its essence, it’s just computers talking to each other. Think about what you do on your computer, such as reading this - this article is stored on a web server somewhere on the internet. Without networking, how would you read it? You might have to get a CD or USB stick to plug in and download it. But thanks to networking, you can send a message to a web server and just ask for it! 

But before we explore the big and scary world of the internet, let's talk about what happens on a Local Area Network. This simply refers to a group of computers in the same geographical area – so a school, business and your home will have a LAN. It’s important for these computers to be able to talk for day to day tasks such as emails and even printing. These networks are normally connected with Ethernet cables or using wireless access points.  

But how do computers know who they are talking to? Firstly, we need to understand that computers on a network have a Network Interface Card (NIC). Every NIC has an address ‘burnt’ into it, which is unique to every NIC worldwide (theoretically – this may not be true but this only matters on a LAN so we don’t need to worry). This address is called the Media Access Control (MAC) address. Every computer has this on a Local Area Network, and it is used address data with, so it arrives at the correct place. A MAC address is 6 bytes long (12 hexadecimal digits) and will look something like 00:1B:44:11:3A:B7. Interestingly, you can also learn a bit about a computer from it’s MAC address; the first half represents the manufacturer of the NIC, then the second half is unique to every NIC made by that manufacturer. The diagram below shows this in detail: 

<img src="https://ssafuze.github.io/EPQ-site/assets/OUI.png">

So, we have addresses for computers on a LAN - great! But how do we know who has those addresses? This is where the Address Resolution Protocol (ARP) comes in. Computers will often only know the IP address (covered later in this article) of the computer it wants to communicate with and doesn’t know it’s MAC address. To solve this, the computer sends an ARP request as a broadcast on the network asking, “hey who has this IP address”. A broadcast means every computer on that network receives this message. When the computer which has that MAC address receives this message, it will respond with “hey that’s me, here’s my MAC address” - now communications can resume as normal. To prevent a request every time they want to send information, and to speed it up, computers have an ARP cache which stores MAC addresses which they have talked to recently. If you are on Windows computer and want to see this, you can type “arp -a” into a command prompt. However, as IP addresses can change on a network, the operating system regularly empties this cache, meaning ARP requests are often resent to get the MAC address again. 

But how do we connect computers on a LAN? The most common solution is to use a switch (as pictured below). This is a device which has multiple computers plugged into it. It works by having a MAC address table, so when it receives a packet addressed to a MAC address, it looks up which port that MAC address is plugged into and forwards the packet on through that port. This is especially useful in a LAN.  

<img src="https://ssafuze.github.io/EPQ-site/assets/switch">

But how do we talk to computers on another network? We don’t use MAC address tables as they would be so long with all the devices that exist! Instead this is where routers come in. A Wide Area Network (WAN) is a collection of LANs interconnected via these routers. The internet is a good example of a WAN - the world’s largest!  

A router acts as a “default gateway” between the LAN and the WAN, and ”routes” traffic between LANs.  It’s basically a switch but between LANs instead of on a LAN. The router will then decide where on the LAN to send the data it received. But instead of a MAC address, routers use IP addresses. Don’t know what this is? We’ll cover it now! 

An IP address acts as a MAC address but is useful for communication between LANs instead of within one. They are made of 4 numbers of 0-255, which means it is 4 bytes long. For example, an IP address may look like 192.168.0.1 (this IP address is actually special as it is a private IP address, but we won’t be looking at this). However, people started to realise that we were running out of IP addresses, due to the large number of devices are communicating today. How do we deal with this? The type of IP address I just showed you was IP version 4 (IPv4), but the new version which is not widely used yet (but does exist) is IP version 6. An example of an IPv6 address is 2001:0db8:85a3:0000:0000:8a2e:0370:7334. This address is written in hexadecimal and provides many, many more possible combinations, so should be suitably future proof! 

Now let's talk about something different - protocols. What’s the point in sending data if the person receiving it doesn’t know what it is? A protocol is a standard set of rules that allow devices to communicate with each other. This means the recipient can understand and interpret what they have been sent and can act on it accordingly. There are a variety of protocols for different tasks, such as HTTP (Hypertext Transfer Protocol) for viewing websites, and FTP (File Transfer Protocol) for sharing files. You can see some of the main ones [here](https://www.interserver.net/tips/kb/common-network-protocols-ports/). 

Finally, we are going to look more in depth at two important protocols, TCP and UDP. Unlike protocols such as HTTP which are focused on the data being sent, TCP and UDP are more focused on how the data is sent.  

Let’s look at TCP. TCP is a “connection-oriented” protocol. This is because it checks to see whether data has arrived at its destination. It starts a conversation with a “3-way handshake” as shown below. Every time data is sent, an acknowledgement (ACK) is sent back. This allows the sender to be sure that the data hasn’t been lost in transit. The alternative is UDP, which does not perform the same checks. It is often referred to as a “fire and forget protocol”, as it doesn’t care whether the data gets there or not – therefore this is often used in movie streaming services as it doesn’t matter if you lose a few little bits of data and is faster than TCP as it doesn’t have any checks on whether data has arrived. 

<img src="https://ssafuze.github.io/EPQ-site/assets/handshake.png">

That was a quick tour of basic networking concepts, and hopefully you picked something up! Feel free to do further research on concepts here that you don’t understand or want to learn about (perhaps using the resources below). I hope you learnt something, and thanks for reading! 

 

Sources for further reading: 

https://www.webopedia.com/TERM/L/local_area_network_LAN.html 

https://standards.ieee.org/faqs/ 

https://erg.abdn.ac.uk/users/gorry/course/inet-pages/ 

https://www.inetdaemon.com/ 

https://searchnetworking.techtarget.com/definition/UDP-User-Datagram-Protocol