## ELO ESY10I1B (ESY10I1-2UWB) Android Tablet (Revision B)

# May 18 2024 Pt2:
Small update. Starting the process to flash build 3.46.50 to see if it fixes the wifi. And/or I may try to make a nandroid backup incase something on newer builds is locked. 
# May 18 2024: 
WORK IN PROGRESS. I am writing this as I do these things. This is as far as I have gone and just stopped to write this out. 

Resuming this project I started a few years back. These ELO tablets (tablet?) are relly cheap. A company I work for pulled their 10" units because they didn't like the size.
There are 2 main revisions to these. Rev A and Rev B. The main differences (that I care about) is Rev A does have a micro USB port for adb/fastboot/etc while Rev B does not.
The only way to interact with ADB etc on Rev B is with a Male USB-A to Male USB-A cable. However, it appears this only works while not in the android OS. ADB does work over wifi though.
Rev B also has the ability to run from POE, while Rev A does not.

You can find many elo products cheap on ebay. Try searching by various part numbers, also try searching something like "Toast Android POS" etc wordings. As these units are
also branded and used by Toast. Same HW, different logo. 

I flashed a patched boot.img from build 3.46.50 on to 3.28.31. I wanted to refrain from updating just incase that may be the only wy to 'recover' while messing with this.
This ended up breaking the wifi (I haven't gone any further yet, I am typing this as I work). Mac address for wifi is corrupt or invalid after flashing. Assuming this
is due to version mismatching etc. And I would imagine it would be fixed once I flash build 3.46.50. 

## Test Tablet Informations:
# ELO ESY10I1-2UWB
- Android 7.1.2
- Kernel 3.18.31
- Build Number 3.28.31

## General Notes:
- Android boot menu = With power off, hold home button (on back of unit), apply power, keep holding until menu. Once and a while it doesn't go. Just try again.
	- [Home] moves through menu
	- [Power] selects 
- ELO View default password = "1elo"
- When USB Debudding is enabled, does work over wifi. 
	- adb connect (ip):5555
	- For USB connection must use a USB-A Male to USB-A Male cable. 
	- Does not work with the micro usb ports.
	- Does not appear to work unless in recovery/fastboot/not the OS. (fastboot does work with USB-A Male USB-A Male)

## Misk Notes:
- OEM Unlocking appeared and I was able to enable after flashing the magisk patched boot.img
- 128gb microSD was unable to be read. Used a 32gb Sandisk Ultra Plus without issues.
- I do not know how to exit the "Please wait" "Excuse us for a moment" whatever loading screen that plays indefinitely when not connected to an ELO View server. A keyboard would probably be useful. 
- Unable to find any jtag, spi, etc pins on the board. Quite possible I was just unable to identify though.
