# Headless Demonsaw Client Setup

This post documents what it takes to setup a Demonsaw client on a Linux host. We chose to document the setup for a Linux host because it is more common to have a headless client or router on a Linux host than on a Windows host.

## Steps
1. Download the Demonsaw
2. Extract the archive and verify permissions
3. Setup your demonsaw config file
4. Launch and test
5. Other considerations

## Download Demonsaw
Demonsaw has builds for multiple operating systems, for Linux you have the [Debian](https://demonsaw.com/#debian) build the [Ubuntu](https://demonsaw.com/#ubuntu) build and the [Raspian](https://demonsaw.com/#raspian) build. Choose the version that you need for your specific Linux distro and download it.

## Extract & Verify
You can extract Demonsaw and run it from wherever you want. If you're running a Demonsaw client off of a headless server it's perfectly fine to put the Demonsaw folder under your home directory. On a desktop Linux Debian distro you might want to put it somewhere better, I like /opt/demonsaw/ so that is what I'll show how to do.

	sudo mkdir /opt/demonsaw
	sudo tar xzf demonsaw.tar.gz -C /opt/demonsaw/

The above command extracts far more than you need for a headless router/client, if you want you can just extract 'demonsaw_cli' with `tar -zxcf demonsaw_cli`, this is also a good way to update demonsaw without over-writing your toml.

Now you need to ensure that the permissions for the /opt/demonsaw/ folder are for your user, in the example our user is named joe.

	sudo chown -R joe /opt/demonsaw

One more important thing to verify is that demonsaw_cli has execute permissions, because sometimes mistakes are made.

	sudo chmod +x /opt/demonsaw/demonsaw_cli

You should now be able to launch demonsaw but you'll be missing the demonsaw.toml configuration, currently the demonsaw_cli will not automatically create this file because it is for a headless client.

## Setup your demonsaw config file
The easiest way to setup the demonsaw config file is to use the GUI to create the setup you want; You can do it from any operating system as the toml is basically the same, just drop the demonsaw GUI binary somewhere like your desktop and run it, add a client and change all the settings to suit your needs, then save the toml and move it over the the machine running the headless client.

If you're in a rush or don't want to fool around with the GUI, below are links to demonsaw config file examples that you can wget from your host and edit.

### toml examples
* [Headless client](../examples/client-demonsaw.toml)
* [Headless client w/ group](../examples/client-w-group-demonsaw.toml)

With the above example toml file you will need to set the client name, the router to connect to, and the paths and files you would like to share.

## Launch & Test
At this point you should be able to launch `demonsaw_cli` from the command line, press `C` to see the status of the client/s. It will take a few seconds of waiting, but it should land on success if everything worked, you should see your clients connected to the router now.

### Startup Scripts
You're now running your own Demonsaw headless client, you probably have it on a VPS somewhere to host files and won't always be able to ssh in to restart demonsaw_cli should it have some issues, or you might not want to have to ssh in just to start demonsaw_cli everytime the server is rebooted; Startup scripts.
There are a few ways to do this, I recommend using [Daniel Stinebaugh's startup script](http://www.stinebaugh.info/demonsaw-startup-script-linux/), but you can start it how ever you would like, including crontab or init scripts.

## Considerations
So you have a working Demonsaw client now, what is next? The cli has a few options for things such as refreshing so that files added to the share are now visible to demonsaw, restart to enable changes to the client configuration, etc.

If you are hosting the headless client on a VPS, you should also think about bandwidth usage as well as the security of your VPS. If your VPS is compromised then some hackers could have the credentials to monitor any secret groups that client was connected to.





