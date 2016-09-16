# Router Documentation
---

##Setting up a router in the GUI
Start by pressing the plus button, and select "router" to create a router and press next. Now choose the (local) name for your router, and enter your local IP or localhost (127.0.0.1) and a port (default is 80, but other common ports can be 8080 and 14480) that is unused.  
__NOTE!__ You might need to port forward your local home router in order to get external connections to your demonsaw router.  
__NOTE!__ Additionally there may be some firewall settings that applies to certain ports and applications.

Now press done, and you've now added a router, and it should turn green to indicate that it's successfully connected.

##Referring additional transfer routers
In the "__Transfer routers__" tab, you can add additional transfer routers to automatically add to connecting clients. This will relieve your router from some of the traffic, and may be helpful if your router is being pushed to its limit.

##Groups
WIP

##Router settings
When you've created your router, there are settings you can change in the options tab.

###Router name
The name of the router is only a local name, and you can name it whatever you want.

###Theme
This is the local theme of your demonsaw GUI. The theme specified here will be applied to your entire GUI, independently of selected client/router within the application.

###Address
This should preferably be 127.0.0.1, as this will start the router on your computer. Specifying the IP of your VPN will not work here!

###Port
This is simply the port you will open to demonsaw traffic.  
__NOTE!__ You might need to port forward your local home router in order to get external connections to your demonsaw router.  
__NOTE!__ Additionally there may be some firewall settings that applies to certain ports and applications.

###Buffer size
You can change the buffer size of your router when it transfers content. This is the amount of data stored temporarily in your memory of data being transferred through your router. the smaller size of your buffer, the lower latency connected clients should have in order to not suffer from lower transfer speeds. The higher buffer you have, the more resources (memory) your router will use while clients are transferring.

###Router type
You can specify what purpose your router serves. If you leave all checkboxes checked, your router will transfer all types of data between the clients connected.

Individually:  
The "__Message__" checkbox will enable this router to transfer chat data between clients. Unchecking this box will make the connected clients unable to chat with each other.  
The "__Transfer__" checkbox enables the transfers of files and other data between clients. Unchecking this checkbox will make connected clients unable to download/upload their shares, unless other transfer routers are referred in the "Transfer routers" tab.  
The "__Public__" checkbox enables clients to chat and browse in a "public group", that is the group clients automatically join if they have no encryption layers specified in their group tab. The public group is often deemed less safe than a private group with additional encryption layers, and are therefore encouraged. Unchecking this checkbox will make clients unable to connect to your router without any encryption layers specified in their group tab.

###Redirect
This textbox enabled your router to function as a redirector, when connected to through a browser. When you connect to your router through a browser, you will automatically be redirected to the URL specified in this textbox.  
__NOTE!__ It does not work to redirect to another demonsaw router, as this redirecting does not affect connections made through demonsaw, only browsers.

###Message of the Day
In this textbox, you can add a message of the day which clients will receive as a message in chat when connecting to your router. You can say anything here.