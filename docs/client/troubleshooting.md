# Client Troubleshooting

Setting up Demonsaw is very straight forward, but sometimes you might run into a simple problem that you overlook. Here we'll cover some of the most common problems when working with Demonsaw, from Client to Router, and aim to be mostly platform neutral.


## Unable to launching Demonsaw

* make sure that demonsaw.xml is in the same directory and has permissions to write to it.
* make sure you are running the correct build for your operating system.
* on *nix based operating system, make sure that demonsaw/demonsaw_cli has execute permissions.

<hr/>

## Connectivity Issues
### Client icon won't stay green
This is usually a sign that your ISP is not handling sockets correctly or your internet could be suffering problems. If it is not either of these it is likely one of the below issues with the router you're connected to.

* Router is running out of entropy
* Too many sockets open to router (Caused by ISP)
* Router is having connectivity issues or DDOS

### Cannot connect to a router

* Make sure router address and port are correct
* Make sure the passphrase is correct, or empty of the router has no passphrase
* Make sure a firewall isn't blocking outbound connections or Internet is working
* If Message or Transfer key/prime size is set too high it could cause a long delay in connecting to a router. If you need to set it lower you will want to also save and restart demonsaw.

<hr/>

## Crashes
If your client crashes when trying to save settings then Demonsaw isn't running with the permissions to save demonsaw.xml.
For most all other crashes it would be a problem with Demonsaw, take note of what you did when the crash occured and report the error with as much detail as possible, there might already be a fix in progress.

<hr/>

## Download/Upload
### Reasons for downloads not starting

* Uploader has a full queue (you're waiting in line)
* Uploader is gone away (No one else has the file for it to be swarmed)
* The message router assigned you to a data router that is busy (you're waiting for your client to retry download from another data router)

### Reasons for uploads not starting

* The data router is busy or slow
* The downloading client is not ready
