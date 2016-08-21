# Demonsaw F.A.Q.

We're going to break the questions down in to three catagories so you can easily find the answers you might have. If you're reading this and have a question you believe should be on here, please let us know in Demonsaw chat.


---

## The Client
#### How am I secure?
You get to pick the level of protection connecting to the message router under the security tab. Even connecting to the public group, you will always have at least one layer of crypto.

#### How am I anonymous?
Demonsaw uses routers to handle all data and communications so that clients never have direct contact, preventing clients from identifying clients. That said, the machines running the routers can see the IP addresses, but it is very difficult to correlate a client to an IP, using a private group will prevent anyone from correlating your IP with a client on the network.

#### What are groups?
Groups allow you to add layers of crypto to your connection to further protect your communications, but groups also isolate you from the public group; 


You can use groups like an especially secure channel on top of the router, where you can communicate and share with a group of friends or create a group for making files available for yourself when you are away from home.

#### Why do I see myself in browse?
This is by design. So that you are able to see your client is working, you can see yourself in the client list and browse (if you're sharing).

#### Why is there an envelope icon next to a message in chat?
This is how Private Messages (PM) are displayed, it is shown in public chat so that you know a message has come through. To open the message you can double-click the sender name or right-click the message and choose "Message".

---

## The Router
#### What role does the router play?
Message routers have several settings allowing you to enable/disable public group, messaging, data transfer, search, and browse. These settings allow you to define what a router supports and how you use it. If you want you can have a message only router and attach data routers to it (like the demonbucket network).

#### What type of information does the router store?
The Demonsaw router doesn't log or save any data, and cannot save any data. It reads the configuration file, it relays messages and data across the network, but nothing is ever written to disk.

---

## The Network
<i>The network is currently hosted and managed by Demonsaw LLC but we are open to adding community provided transfer routers to the mix since clients have the option to deselect routers they don't trust.

The below are a few questions and answers regarding this network and demonsaw networking in general.</i>

#### What is router.demonsaw.com?
This is the Demonsaw public message router, where messages, browse, and search is performed. It should be viewed as a sample network to show off how Demonsaw works, how you can use Demonsaw on your network, and to see how well Demonsaw can scale.

#### Why are my file transfers going through different routers?
To scale our ability to provide high speed and high bandwidth file transfers, we have disabled transfer on the message router (router.demonsaw.com) and added transfer routers to the message router. Additionally, Demonsaw 3 distributes each file transfer across multiple transfer routers for speed and extra anonymity (this is called sharding).

