---
title: Make Mac Downloads Folder Sync to iCloud
excerpt: "Configure the Downloads folder on a Mac to sync to iCloud just like it is possible for Desktop and Documents folders."
description: "Configure the Downloads folder on a Mac to sync to iCloud just like it is possible for Desktop and Documents folders."
categories: [Administration]
tags: [files and folders, mac]
---

On a Mac, you can enable iCloud sync for your Desktop and Documents folder. This will sync all files in those folders accross all your devices, oncluding mobile devices such as iPhone or iPad.
How to do so is described [here](https://support.apple.com/en-us/HT206985).

This does not include your Downloads folder, though. But there is an easy way to sync the Downloads folder as well:

0. First, move all your files from `~/Downloads` to the new location. For example, your iCloud Downloads

(`/Users/$USER/Library/Mobile Documents/com~apple~CloudDocs/Downloads`)

or Dropbox Downloads

(`/Users/$USER/Dropbox/Downloads`).

0. Second, backup `.localized`:
	```
	cp -av Downloads/.localized ~/
	```
0. Next, remove `~/Downloads`:
	```
	sudo rm -rf Downloads/
	```
0. Then create a symlink to your target folder, for example iClouds Downloads or Dropbox downloads (see above):
	```
	ln -sv ~/Dropbox/Downloads ~/Downloads
	```
	Or, for iCloud:
	```
	ln -sv ~/Library/Mobile\ Documents/com\~apple\~CloudDocs/Downloads ~/Downloads
	```
0. Restore `.localized` backup:
	```
	mv ~/.localized ~/Downloads/
	```
0. Restore folder permissions:
	```
	chmod -h 700 ~/Downloads
	```
0. Done! Your `~/Downloads` is now synced!