# Demonsaw F.A.Q.

We're going to break the questions down in to three catagories so you can easily find the answers you might have. If you're reading this and have a question you believe should be on here, please let us know in Demonsaw chat.

---

## The Client
#### How am I secure?
You get to pick the level of protection connecting to the message router under the security tab. Even connecting to the public group, you will always have at least one layer of crypto.

#### How am I anonymous?
Demonsaw uses routers to handle all data and communications so that clients never have direct contact, preventing clients from identifying clients. That said, the machines running the routers can see the IP addresses, but it is very difficult to correlate a client to an IP, using a private group will prevent anyone from correlating your IP with a client on the network.

#### What are groups?
Groups allow you to add layers of crypto to your connection to further protect your communications as well as isolating you from the public group; You can use groups like an especially secure channel on top of the router, where you can communicate and share privately.

#### Why don't I see myself in browse?
This is by design. You will not see your own client in browse, your shared files in search, or your client in the message list.

---

## The Router
#### What role does the router play?
Message routers have several settings allowing you to enable/disable public group, messaging, data transfer, search, and browse. These settings allow you to define what a router supports and how you use it. If you want you can have a message only router and attach data routers to it (like the demonbucket network).

#### What type of information does the router store?
The Demonsaw router doesn't log or save any data, and cannot save any data. It reads the configuration file, it relays messages and data across the network, but nothing is ever written to disk.

---

## The Network (Official Public Router)
<i>The network that Demonsaw connects to by default is the official Demonsaw public router. It is fully funded and provided by Eijah with a few community routers that were contributed to add bandwidth to the network. It is to show off how you can use Demonsaw and to test how well it can scale. The below are a few questions and answers regarding this network and demonsaw networking in general.</i>

#### What is router.demonsaw.com?
This is a sample network, the tutorial level, a public example of the type of network you can create with Demonsaw.

#### Why are my file transfers going through different routers?
To scale our ability to provide high speed and high bandwidth file transfers, we have disabled transfer on the message router (router.demonsaw.com) and added transfer routers to the message router. Some or possibly most of the transfer routers are contributed and operated by community members.

#### How does Demonsaw determine what data router I get?
Demonsaw 'shards' file transfers, this means that file transfers are broken up and transferred through multiple transfer routers at once. To transfer a single file, depending on the size of the file, Demonsaw can transfer the file across anywhere between 1 to 8 transfer routers at once.
