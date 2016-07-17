# Short Intro to Demonsaw

## Overview

Demonsaw is a secure and anonymous information sharing application that makes security simple and gives you back control of your data. Demonsaw provides you with a way to create your own network or join a public Demonsaw network so that you can share and communicate securely.


## Getting Started

First thing first! You need to [download Demonsaw](https://demonsaw.com/)!

Demonsaw is provided without installers, as a stand-alone application so that it can be run from or stashed anywhere you want. Just download the version you need for your operating system, extract it somewhere, and launch Demonsaw.

#### Want an Installer?

The community (dekka) has provided a Linux repository for Debian and Ubuntu, and also has rpm packages for Fedora/Redhat.

Want to learn more? Check out [repo.dsrouters.com](https://repo.dsrouters.com/)

## How it Works

This section will be a rough overview of how Demonsaw works, how it is designed to protect you, and will hopefully take some of the confusion out of the network.

### Communication

TL;DR;

* Clients do not communicate with clients, Demonsaw is not peer to peer. 
* All client communication goes through message routers and data routers.

If you were to sniff your local traffic and peer into the Demonsaw communication, you'd see TCP traffic that looks just like HTTP web traffic... but with encrypted payloads. Clients can pass user-agent strings, making them appear more like a web browser. Demonsaw routers can listen on any port you want, including 80 and 8080, and can even redirect actual web browsers to another website with a 301 permanent redirect.

In essence, Demonsaw clients and routers are both behaving as both an HTTP server and a client, allowing them to send messages and data back and forth all while looking like normal web traffic.



### Crypto

TL;DR;

* You specify the security of the crypto handshake, you control your level of protection.
* At minimum, your communication is wrapped in two layers of crypto.

<!-- <p style="color:red;font-weight:bold;">More details are needed from Eijah</p> -->
Demonsaw allows you to choose your own level of security through cryptography, both through the first handshake with a router and through the use of groups setup with social cryptography. Demonsaw uses Diffie–Hellman key exchange to connect securely, but allows you to define the prime size, cipher, key size, hash type, salt, and how many iterations.

![router handshake settings](../img/screenshots/routerhandshake.png)

On top of the encrypted connection to a Demonsaw router, a second layer is added for the public group.

If you want to connect to a public router but be hidden from the public group, you can add crypto layers through the additions of groups. Unlike the router crypto settings, you also get to define a file or passphrase as the source of entropy, allowing for extra secure cryptographic layers. Additionally, you can add as many layers as you want.
![group settings](../img/screenshots/GroupSettings2.png)


## Demonsaw Overview (Slides)

<script async class="speakerdeck-embed" data-id="9b96353422ec4dc988a6e0f26c28c437" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script>
<!--
<iframe width="100%" height="480px" frameborder="no" scrolling="no" class="embed-responsive embed-responsive-16by9" src="net-diagram.html" style="background-color:transparent;border:0;"></iframe>
-->

