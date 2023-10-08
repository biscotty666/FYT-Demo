---
fileClass: [article, project]
---
%%
topic:: [[Technology]]
related:: [[Obsidian]]
created:: 2023-08-23
last edit:: 
status:: 100
author:: Brian Carey
title:: Syncing Your Thinking with Syncthing
Project Name:: New Site
Item Notes:: 
Item Status:: alpha
Action Note:: 
link:: 
action:: false
Published to:: Medium.com, SubStack, biscotty..online, lemmy.world
Author:: 
Stage:: published
PubDate:: 2023-08-28 Mon
Item Action:: Final Review, Lemmy Links
Published:: true
Cover:: 
aliases:: 
type:: article
%%
# Syncing Your Thinking with Syncthing

## Fast, Secure, Private, Free

Obsidian loses a lot of power if you can't take notes from anywhere at anytime on any device you are using. Obsidian offers a subscription syncing service about which I've seen no complaints.

But there is an awesome [free, open source](https://biscotty.online/technology/foss) project called [Syncthing](https://syncthing.net) which is ideal for Obsidian. It's easy to install on any OS or device, with almost instantaneous syncing, and it's 100% private.

## Device-to-Device Sync

Most people are familiar with synchronization approaches which involve a central server, or at least a central, usually cloud-based, directory. This approach is commonly used to keep both multiple people and potentially multiple directories, and even development environments, synchronized.

In Obsidian we don't need something so fancy. If you aren't sharing (collaborating) on your vault, and if you don't use two devices simultaneously 😉, the device-to-device synchronization is what you need. It is rapid, secure and private. Your information never sits anywhere other than on your own devices.

Device-to-device connections use a protocol called Universal Plug and Play, or UPnP. These do use a central server, but only for the purposes of locating and connecting devices, not for file transfer. When a device with Syncthing running connects to the internet it announces it's location to the server and retrieves the location of your other on-line devices, to which they make a direct connection.

Once connected the devices share data directly with each other.  Synchronization is very rapid. For example, sometimes I like to dictate my notes on my phone. I can have the note open on both my phone and my computer, dictate into my phone, and the text appears almost instantly in the note open on my computer.

## Setup

Syncthing is available on all common operating systems. I use a Linux operating system with an Android phone, but setup should be the same on any devices. On Linux the easiest and probably best way is with the flatpak. Most distros have `flatpak` installed by default, so: 

```
flatpak install flathub com.github.zocker_160.SyncThingy
```
On other OSs and devices you can use the normal installation process by going to their [website](https: syncthing.net). (Isn't Linux easier?)

Getting you vault synchronized is a two-step process:

1. Connecting the devices
2. Sharing the directories
### Connecting Devices
Devices are connected by exchanging Device IDs, which are long alphanumeric strings. The connection can be initiated from either the computer or the phone. Syncthing will display a QR code containing the Device ID, so the most convenient way is to display the computer's code, scan it with a phone and initiate the connection from the phone.

The Syncthing interface can be accessed using your web browser (localhost:8384). From the browser interface, show the QR code on the computer.

![[SyncthingShowQR.jpg]]

On the phone, in the devices tab, click on the `+` to add a device, and then the QR symbol to scan the code. After that, give the device a meaningful name and save the new device.

![[ST-Phone-Device.png]]

Back on your computer you will see an alert asking if you want to add the phone device. Accept this and give the device a name.

![[ST-add-device 1.jpg]]

After accepting the device and after a short period the devices will display connected. This may take a few minutes the first time, but don't worry...if you scanned the QR code nothing can really go wrong.
### Sharing Directories 
The first thing to do is create a directory on your phone for your Obsidian vault. 

Once the devices are connected you can start to share directories. Since this is an Obsidian tutorial we only need to share the vault directory, but you can use the same process to share, for example, your photo or image directories on your phone so that you automatically get copies on your computer.

When we add (and delete) Syncthing directories, we aren't really adding or removing any directories or files. We are adding an identifier which points to a directory on your device or system. So deleting a Syncthing directory is an entirely safe process.

That said, go ahead and add a Syncthing directory on your computer. Give the directory a specific name (Obsidian, maybe) and point it to the directory on your computer which contains your vault.

![[SyncthingAddFolders2 1.jpg]]

In the sharing tab, select your phone or other device.

![[SynthingLappyAddDevice.jpg]]

As when we added a device earlier, an alert will appear, this time on your phone. Accept to add the offered directory, and you will be prompted to give the directory a name and location. The name may or may not be the same as the one on the computer, since Syncthing is actually using the long, auto-generated string in the middle which you left alone, right?

Then select the new directory we created earlier as the location, and that's it. Depending on the size of the files in the directory the initial sync can take a while. Since Obsidian files are just text files even the initial sync should be rapid. If you are syncing your phone images, the initial sync can take hours. Once they are synced, though, images from your phone will appear on your computer in seconds.
## Closing Thoughts
From the wonderful world of FOSS we have a synchronization tool ideal for keeping directories in sync across personal devices. Perfect for Obsidian!

