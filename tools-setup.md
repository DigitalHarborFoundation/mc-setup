# Programming Minecraft With Python

## Overview
This document includes instructions for setting up a development environment for Python and MinecraftEDU on macOS. This is a series of steps pieced together from various sources. I was unable to find a specific set of instructions for integrating the Python Minecraft API with MinecraftEDU. I was able to piece together various tools and installations processes to make this environment work.

Much of this guide is adapted from [this blog post](https://www.epiphanydigest.com/2016/03/07/learn-to-program-with-minecraft-on-ubuntu/). I converted much of it to work with MinecraftEDU.

For now, this is largely a series of steps to follow. More explanation will be included at a later point.

## PyCharm
Install the PyCharm IDE. One concern I had was that this wouldn't interact with the Minecraft environment, but the PyCharm interpreter works perfectly with Raspberry Juice and the Minecraft API.

Here's a download link for the free edition.
[PyCharm Community Edition: Mac](https://www.jetbrains.com/pycharm/download/#section=mac)

- Download the package and install it into the Applications folder.
- Optional: Pin to the Dock.

## Minecraft Tools
I grouped together all of the server tools that are needed in the environment. I packaged them into a zip folder.

- Download link for the tools: [Minecraft Tools Pack](http://dhf-website.s3.amazonaws.com/files/minecraft-tools.zip)
- Download the .zip and move it from _Downloads_ to _Documents_.
- Once in _Documents_, expand the zip to create the **minecraft-tools** folder.

## Installing Prerequisites and Dependencies
While going through this process I encountered that there were several prerequisite installations as well as many dependencies. I've included this in this section, going as far back to the first trackable dependency. You may already have some of these installed on your Mac system.

### Install Homebrew
- Install the Homebrew package manager. Check out their install page here: [Homebrew install](https://brew.sh/)
- Open _Terminal_ and enter the following code into the command prompt:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
- This process may take awhile. If you see lots of action in the Terminal window, Homebrew is installing correctly.

### Install Python3
- The courses uses Python3, which may or may not be installed.
- Open Terminal and enter the following command:
```bash
brew install python3
```
- This will either install Python3, or verify that it's already installed. If you see "Warning: python3 3.6.1 is already installed" then your system already has the latest version of Python3.

### Install Java
- Use Homebrew to install the latest Java SDK. This is needed to run MinecraftEDU.
- Type the following into Terminal and press enter:
```bash
brew cask install java
```

### Minecraft API

- At this point, navigate to the **minecraft-tools** folder that you made in your _Documents_ folder.
- The following series of instructions require you to be inside this directory. The installation won't work if you're not!
- Open a Terminal prompt, and navigate to this file location by typing the following:

```bash
cd ~/Documents/minecraft-tools
```
- This will _change directories_ to the **minecraft-tools** folder.
- At this point, type the following command into Terminal:

```bash
pip3 install ./py3minepi-master
```
- The ./ is crucial! This installs this particular package from the current folder.

Note: You may need to use **sudo** for this. If so, use sudo and enter an admin password.

## Testing
To test that the server is installed, run the following command in Terminal:

```bash
./start.sh
```

This will execute the script that launches the server. You _must keep Terminal open!_ Closing Terminal closes your server!

## Conclusion
The tools should now be installed! I pre-packaged much of the heftier installations by bundling everything into the minecraft-tools zip. Make sure to keep this folder intact!
