# Router Troubleshooting

Setting up a Demonsaw router takes a bit more effort than starting a client. Here we'll cover troubleshooting steps that will apply to both the headless demonsaw_cli and a Demonsaw router that you started from GUI.

## Issues starting the router

* (*nix) Make sure demonsaw_cli has execute permissions
* (*nix) If the router is setup for a port below 1024, the router must be run with sudo or moved to a higher port.

<hr/>
## Connectivity Issues
### Clients cannot connect

* (*nix) If the router is setup for a port below 1024 the router must be run with sudo or moved to a higher port.
* Make sure that the router is listening on the correct IP Address. (DO NOT USE 0.0.0.0, localhost, 127.0.0.1, etc)
* Make sure that the router port is not blocked by firewall.
* If router is behind a gateway, make sure the port is forwarded to allow outside network connections.
* Verify that a passphrase wasn't set on the router or the clients are using the correct passphrase.
* Verify that the clients are using the correct port number to connect to the router.
* If connecting to the router by domain name, make sure DNS is working correctly.

<hr/>
## File transfer Issues
The notes are assuming that all clients are unable to perform file transfers.

* Ensure that transfer and timeout settings are at defaults. (no crazy changes or errors in configuration)
* Ensure that transfer is enabled in the router config. (<transfer>true</transfer> under action)
* Ensure that the router hasn't run out of connection sockets or bandwidth.
* Check that any data routers added to the 'server' section are in working order.


<hr/>
## Reliability Issues
### Clients bouncing (Client color bounces between green and blue)

* Server could be out of entropy
