# Demonsaw F.A.Q.

We're going to break the questions down in to three catagories so you can easily find the answers you might have. If you're reading this and have a question you believe should be on here, please let us know in Demonsaw chat.

<i>This FAQ will information that applies to Demonsaw 2 & 3 but will be revised for the release of Demonsaw 3.0</i>

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

## The Network (DemonBucket)
<i>The network that Demonsaw connects to by default is a network started by Demonbucket and was fully funded and provided by Demonbucket and the community. It is to show off how you can use Demonsaw and to test how well it can scale. The below are a few questions and answers regarding this network and demonsaw networking in general.</i>

#### What is bucket1.demonbucket.com?
This is a sample network created by Osteth of Demonbucket, a public example of the type of network you can create with Demonsaw.

#### Why are my file transfers going through different routers?
To scale our ability to provide high speed and high bandwidth file transfers, we have disabled transfer on the message router (bucket1.demonbucket.com) and added transfer routers to the message router.

#### How does Demonsaw determine what data router I get?
The message router goes through the router list in round robin, grabbing the first available data router.
