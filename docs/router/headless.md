# Headless Demonsaw Router Setup

This post documents what it takes to setup a Demonsaw router on a Linux host, the process is very simple but we'll cover the thinks to look out for and things to think about when setting up a router.

## Steps
1. Download the Demonsaw
2. Extract the archive and verify permissions
3. Setup your demonsaw config file
4. Launch and test
5. Other considerations

## Download Demonsaw
Demonsaw has builds for multiple operating systems, for Linux you have the [Debian](https://demonsaw.com/#debian) build the [Ubuntu](https://demonsaw.com/#ubuntu) build and the [Raspian](https://demonsaw.com/#raspian) build. Choose the version that you need for your specific Linux distro and download it.

## Extract & Verify
You can extract Demonsaw and run it from wherever you want. If you're running a Demonsaw router off of a headless server it's perfectly fine to put the Demonsaw folder under your home directory. On a desktop Linux Debian distro you might want to put it somewhere better, I like /opt/demonsaw/ so that is what I'll show how to do.

	sudo mkdir /opt/demonsaw
	sudo tar xzf demonsaw.tar.gz -C /opt/demonsaw/

The above command extracts far more than you need for a headless client/router, if you want you can just extract 'demonsaw_cli' with `tar -zxcf demonsaw_cli`, this is also a good way to update demonsaw without over-writing your toml.

Now you need to ensure that the permissions for the /opt/demonsaw/ folder are for your user, in the example our user is named frank.

	sudo chown -R frank /opt/demonsaw

One more important thing to verify is that demonsaw and demonsaw_cli have execute permissions, because sometimes mistakes are made.

	sudo chmod +x /opt/demonsaw/demonsaw_cli

You should now be able to launch demonsaw but you'll be missing the demonsaw.toml configuration, currently the demonsaw_cli will not automatically create this file because it is for a headless router.

## Setup your demonsaw config file
The easiest way to setup the demonsaw config file is to use the GUI to create the setup you want; You can do it from any operating system as the toml is basically the same, just drop the demonsaw GUI binary somewhere like your desktop and run it, add a router and change all the settings to suit your needs.

If you're in a rush or don't want to fool around with the GUI, below are links to demonsaw config file examples.

### toml examples
* [Headless Router](../examples/router-demonsaw.toml)
* [Headless Router and Client](../examples/router_and_client-demonsaw.toml)

With any of the above example toml files you will need to set the address to the external IP Address for the router, the Download and Share paths must be valid (it's recommended to leave a trailing slash), passphrase is left empty so you can easily fill it in if needed. And examples with groups need to be changed to match your group setup.

## Launch & Test
At this point you should be able to launch `demonsaw_cli` from the command line, press `C` to see the status of the client/router. It will take a seconds of waiting, but it should land on success if everything worked.

## Considerations
So you have a working Demonsaw router now, what is next? If you plan to scale and build your own private network then you still have a few things that you'll want to work on.

### Startup Scripts
You're now hosting your own Demonsaw network, you probably have it on a VPS somewhere and won't always be able to ssh in to restart demonsaw_cli should it have some issue, or you might not want to have to ssh in just to start demonsaw_cli everytime the server is rebooted; Startup scripts.
There are a few ways to do this, I recommend using [Daniel Stinebaugh's startup script](http://www.stinebaugh.info/demonsaw-startup-script-linux/).

### Adding data routers
The above toml examples are setup so that the router you setup handles the messaging, client search and browse, and the data transfers. If you've ever connected to the Demonbucket network you'll notice that you connect to Bucket1 but when you download something your download goes through another router. You can add as many data routers as you want, in Demonsaw 2.x these are just normal Demonsaw routers (you can disable messaging, search/browse, etc if you want). The easiest way to set this up is again to use the GUI and get your configuration as close as you want it, save it, then edit and move the demonsaw.toml to the router you want to use it on.

### Entropy (Linux hosts only)
Your Demonsaw router, even with 10 people connecting, is using more crypto than a simple https site with 10 people connected. Everything you do in Demonsaw is encrypted, and each client connecting drains a bit of entropy from the server you're running the Demonsaw router off of.
For a Demonsaw router you will want an entropy pool size around 2500 or higher, you can check your entropy with the below command.

	watch cat /proc/sys/kernel/random/entropy_avail

There are a few ways to boost your entropy if it is low, the easiest is to install `Haveged` or `rng-tools` or both. Below are the commands for Debian, but both tools should be available for other Linux distros. Once you install them you can check your entropy again, you should see an immediate boost.

	sudo apt-get install haveged
	sudo apt-get install rng-tools

Keeping your entropy at a usable value will prevent your router from having handshake issues when you start to build your userbase.