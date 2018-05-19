# Getting started

First of all you have to put together at least all the required hardware parts:

{% page-ref page="../what-do-you-need.md" %}

Then, you have to run the software on your Raspberry. **OpenPlotter** is a modified version of [Raspbian](https://www.raspbian.org/), the official operating system for the Raspberry Pi. It contains all you need. OpenPlotter is open-source and free.

## Installing OpenPlotter

Raspberry Pi, and most embedded systems, uses an SD card as Hard Disk. Almost any micro-SD-compatible card will work on your Raspberry.

{% hint style="warning" %}
A minimum of 8GB is required but 16GB is recommended.
{% endhint %}

To begin with, it's always a good idea to make sure you have formatted your SD card. You'll need to make sure your computer has a built-in SD card reader, or you can use an USB SD card reader.

* Visit the [SD Association’s website](http://www.sdcard.org//) and download [SD Formatter](https://www.sdcard.org/downloads/formatter_4/index.html) program for either Windows or Mac.
* Follow the instructions to install the software.
* Insert your SD card into the computer or laptop’s SD card reader and make a note of the drive letter allocated to it, e.g. `F:/`
* In SD Formatter, select the drive letter for your SD card and format it.

![SDFormatter V4.0](../.gitbook/assets/sd-formatter.jpg)

{% hint style="warning" %}
If your SD card has 64GB or more, it will automatically be formatted as exFAT, which is not compatible with OpenPlotter. Follow [these instructions](https://www.raspberrypi.org/documentation/installation/sdxc_formatting.md) to force your SD card to format as FAT32 so that you can use OpenPlotter.
{% endhint %}

* Download the latest NOOBS installer version of **OpenPlotter.** It is a compressed file of about 1GB so it will take a while. 
* Extract the files from the zip.
* Drag all the files in the extracted NOOBS folder and drop them onto the SD card drive.
* The necessary files will then be transferred to your SD card.
* When this process has finished, safely remove the SD card and insert it into your Raspberry Pi.

![](../.gitbook/assets/boot1.png)

## First boot

Connect power to the Raspberry Pi.

OpenPlotter NOOBS installer will make a silent install, this means that you have to do nothing. It will take several minutes to format partitions and install the system.

Once the OpenPlotter NOOBS installer has installed the system, OpenPlotter will start directly every time we connect the Raspberry Pi.

![OpenPlotter startup window](../.gitbook/assets/startup.png)

The native monitor resolution for 800x480 monitors will be auto detected. The right settings for it will work on the next boot! If you have such a monitor, restart.

You can also run OpenPlotter without monitor \(headless\) using any laptop, desktop computer, tablet or smart-phone as a remote desktop client.

{% page-ref page="headless.md" %}

## First settings

Go to _Menu &gt; Preferences_ and select _Raspberry Pi Configuration_

![](../.gitbook/assets/rpisetup1.jpg)

A window will open where you can personalize your system. 

![](../.gitbook/assets/rpisetup3.jpg)

{% hint style="danger" %}
It is a good idea to change the password to make OpenPlotter more secure. Click on _Change Password_ \(default password: raspberry\).

If you do not change the password, anyone will be able to connect to OpenPlotter remotely. Please do it now.
{% endhint %}

If you need to set your system localisation, click on the _Localisation_ tab and then on _Set Locale_ \(language\), _Set Timezone, Set Keyboard_ and _Set WiFi Country_ buttons.

![](../.gitbook/assets/rpisetup2.jpg)

### Signal K settings

Signal K server provides many useful tools and you will have to visit its administration panel often. Go to _Menu_ &gt; _OpenPlotter_ &gt; _Signal K._

#### Password

Data visualization is open but settings is under authentication. Press _Login_ button upper right.

User name: openplotter  
Password: openplotter

![](../.gitbook/assets/sk_login.png)

{% hint style="danger" %}
Please change this password as soon as possible. Login and go to _Signal K_ &gt; _Security_ &gt; _Users_ &gt; _openplotter_
{% endhint %}

#### Vessel data

If you are going to share data with other boats you should have an unique identifier. Login to Signal K and go to _Server_ &gt; _Vessel_ _data_ and change at least your bot name and MMSI.

Here you can also provide data about your boat that could be useful for some Signal K tools.

![](../.gitbook/assets/sk_vessel_data.png)

## Updating {#updating-openplotter}

From OpenPlotter  v0.10.0, you can update your installation without need of burning a new SD card.

Be sure you are connected to Internet and go to _Updates_ in the OpenPlotter main menu and then to _Update OpenPlotter_. OpenPlotter will check if you need to do a minor or a major update and it will do all the work for you.

You can also update OpenCPN and plugins to the latest stable releases and restore the desktop settings if it has changed after an update.

![](../.gitbook/assets/update.png)

### Version numbering {#version-numbering}

OpenPlotter releases have three numbers: **a**.**b**.**c** \(v0.10.0, v1.0.0...\) and a word \(**alpha**, **beta** and **stable**\).

When **c** increases, there is a minor change and means that only the OpenPlotter code has changed. When **b** increases, there is a major change and means that other packages or dependencies need to be added or updated too. When **a** increases, there is an upgrade and means that Raspbian needs to be upgraded. In this case a new OpenPlotter image will be released and you have to burn a new SD card.

**Alpha** means that some parts still need development. **Beta** means that all parts have been developed and there are not fatal errors but it needs to be tested by users in different scenarios. Text will be translated from English into other languages on this stage. **Stable** means that OpenPlotter code and dependencies have already been tested and there are not errors.

You can know what version you are running selecting the option _About_ in _Help_ menu.

![](../.gitbook/assets/about.png)

## Backup

## Recovery system

If our system gets damaged or unstable, we can recover it from the NOOBS installer that resides on your SD and install OpenPlotter again. Press the Shift key when you see this symbol at startup:

![](../.gitbook/assets/recovery.png)

{% hint style="danger" %}
**You will lose all data, manually installed programs and settings after recovering.**
{% endhint %}
