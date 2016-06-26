# Demonsaw 3.0+ Documentation

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



## The Network
blah

## More Resources
blah