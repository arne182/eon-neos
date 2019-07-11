How to go back to 05 if you have installed 06 before
======

This is the operating system for your [EON Dashcam Development Kit](https://shop.comma.ai/products/eon-dashcam-devkit).

It's open source, you can find the repo needed to build NEOS [here](https://github.com/commaai/eon-neos-builder)


------

Requirements: unzip, simg2img, fastboot

Clone this repo. Hold power and volume to enter fastboot mode on your EON. Then run:

You can use homebrew to install: 

1. Install homebrew

```
ruby -e “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. Install adb (fastboot)

```
brew cask install android-platform-tools
```

3. Install simg2img
```
brew install simg2img
```

Hold power and volume to enter fastboot mode on your EON or Android device. 

Connect it via USB to your MAC.

Navigate to the direction, wehre your files are and run:

```
/download.py ./flash.sh
```

After a while your eon will reboot and ask you: "Enter the URL of the NEOS program to install"

Type in:

```
openpilot.comma.ai
```

It will download and install official comma 06. 

After rebooting a purple screen will appear: 

![enter image description here](https://cdn.discordapp.com/attachments/555026950067060736/597766347031838723/image0.jpg)


Do not klick anything. 

From here you need to install 05.11 original comma:

ssh in and: 

```
cd /data; cp -rf ./openpilot ./openpilot.bak; rm -rf ./openpilot; git clone https://github.com/arne182/openpilot.git openpilot; cd openpilot; git checkout 0511-final
```

Restart your eon and it will boot on 05.11 branch. 

From here you can install every awesome fork with great mapd support for example ;) - Like arnes realse 2 :

https://github.com/arne182/openpilot/tree/release2



<b>NOTE: This will wipe your EON</b>

Restoring on OS X
------

1. Install Homebrew if you don't already have it. It's like apt-get for OS X (a package manager) https://brew.sh
2. `brew install unzip simg2img` which will be needed to build the image
3. `brew cask install android-platform-tools` to install fastboot, which will be required to actually flash your Eon
4. Put your Eon into fastboot mode by turning off your Eon, then holding EON: volume up + power. EON Gold: volume down + power. Select fastboot if needed from the menu.
5. Clone this repo, then cd into the cloned repo and run `./download.py`
6. When done, run `./flash.sh` Your Eon will now be flashed. DO NOT DISCONNECT THE DEVICE!
7. Congratulations! You may now setup your Eon again.

Restoring on Linux
------
Submit a PR with instructions.

Restoring on Windows
------
Submit a PR with instructions.
