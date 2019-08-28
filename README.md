Downgrade from 0.6 to 0.5 
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

``` 
git checkout 45ce1790dd5f4ef8ef5987fa198a904b69b9ce53
```

{
  "ota_url": "https://commadist.azureedge.net/neosupdate/ota-signed-fbbb6b1ce9eab4f3cee3ee4d1f19a1d9714b05f8aec44a41104446d3d683e36a.zip",
  "ota_hash": "fbbb6b1ce9eab4f3cee3ee4d1f19a1d9714b05f8aec44a41104446d3d683e36a",
  "recovery_url": "https://commadist.azureedge.net/neosupdate/recovery-df61ad77c40b31ae18e147b3bd82d4edf6d5f0483642e8c62a2b63754e57cc19.img",
  "recovery_len": 15136044,
  "recovery_hash": "df61ad77c40b31ae18e147b3bd82d4edf6d5f0483642e8c62a2b63754e57cc19"
}

Hold power and volume to enter fastboot mode on your EON or Android device. 

Connect it via USB to your MAC.

Navigate to the direction, wehre your files are and run:

```
./download.py 
./flash.sh
```

After a while your eon will reboot and ask you: "Enter the URL of the NEOS program to install"

Type in:

```
https://openpilot.comma.ai
```

It will download and install official comma 06. 

After rebooting a purple screen will appear: 

![enter image description here](https://cdn.discordapp.com/attachments/555026950067060736/597766347031838723/image0.jpg)


Do not click continue. Click wifi and set up your wifi settings 

From here you need to install 05.11 original comma:

ssh in and [guide for ssh](https://medium.com/@jfrux/comma-eon-getting-connected-with-ssh-3ed6136e4a75): 

```
cd /data; cp -rf ./openpilot ./openpilot.bak; rm -rf ./openpilot; git clone https://github.com/arne182/openpilot.git openpilot; cd openpilot; git checkout 0511-final
```

Restart your eon and it will boot on 05.11 branch. Log into gmail account. Switch on the OSM feature and set your offset. 

Can only be done after you fingerprint your car and if you have longitudinal control.

From here you can install every awesome fork with great mapd support for example ;) - Like arnes realse 2 :

[Arne's fork](https://github.com/arne182/openpilot/tree/release2)



<b>NOTE: This will wipe your EON</b>



Restoring on Linux
------
Submit a PR with instructions.

Restoring on Windows
------
Install python 2.7 from https://www.python.org/downloads/

git checkout 45ce1790dd5f4ef8ef5987fa198a904b69b9ce53

{
  "ota_url": "https://commadist.azureedge.net/neosupdate/ota-signed-fbbb6b1ce9eab4f3cee3ee4d1f19a1d9714b05f8aec44a41104446d3d683e36a.zip",
  "ota_hash": "fbbb6b1ce9eab4f3cee3ee4d1f19a1d9714b05f8aec44a41104446d3d683e36a",
  "recovery_url": "https://commadist.azureedge.net/neosupdate/recovery-df61ad77c40b31ae18e147b3bd82d4edf6d5f0483642e8c62a2b63754e57cc19.img",
  "recovery_len": 15136044,
  "recovery_hash": "df61ad77c40b31ae18e147b3bd82d4edf6d5f0483642e8c62a2b63754e57cc19"
}


run the python script to download the files.

Unzip the ota file to the same folder. So move the system.img/boot.img out of the "/files" one folder up!!!

img2simg.exe from  https://forum.xda-developers.com/showpost.php?p=49235638&postcount=5

fastboot.exe from https://forum.xda-developers.com/showthread.php?t=2588979

img2simg.exe system.img system.simg

fastboot.exe flash recovery recovery.img

fastboot.exe flash boot boot.img

fastboot.exe flash system system.simg

fastboot.exe erase userdata

fastboot.exe format cache

fastboot.exe reboot

After a while your eon will reboot and ask you: "Enter the URL of the NEOS program to install"

Type in:

```
https://openpilot.comma.ai
```

It will download and install official comma 06. 

After rebooting a purple screen will appear: 

![enter image description here](https://cdn.discordapp.com/attachments/555026950067060736/597766347031838723/image0.jpg)


Do not click continue. Click wifi and set up your wifi settings

From here you need to install 05.11 original comma:

ssh in and [guide for ssh](https://medium.com/@jfrux/comma-eon-getting-connected-with-ssh-3ed6136e4a75): 

```
cd /data; cp -rf ./openpilot ./openpilot.bak; rm -rf ./openpilot; git clone https://github.com/arne182/openpilot.git openpilot; cd openpilot; git checkout 0511-final
```

Restart your eon and it will boot on 05.11 branch. Log into gmail account. Switch on the OSM feature and set your offset. 

Can only be done after you fingerprint your car and if you have longitudinal control.

From here you can install every awesome fork with great mapd support for example ;) - Like arnes realse 2 :

[Arne's fork](https://github.com/arne182/openpilot/tree/release2)



<b>NOTE: This will wipe your EON</b>
