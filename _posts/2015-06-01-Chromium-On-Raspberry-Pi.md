---
title: Chromium on Raspberry Pi
layout: post
tags:
- News
- RPi
- uBuntu
- Chromium
---

*Written by Yasmin*

*Edited by Jianing*

<p>Our first step to provide a stable coding platform on Raspberry Pi is to install an operating system compatible with Chromium - a browser necessary to run the Google Chrome App, Espruino. Espruino is our favorite app to send commands to the SMAC robot, but it’s only supported by Chromium 23 or later versions. With a limited pool of operating systems to choose from, we started off with Raspberry Pi’s recommended OS image: Raspbian.</p>

<p>First, we tried to install Chromium with the current source code provided by previous Raspberry Pi users:	</p>

>$sudo apt-get install chromium
>
>$sudo apt-get update

<p>Unfortunately, executing the above commands on the root of Raspberry Pi Model B in Raspbian proved unsuccessful. The Chromium browser installed turned out to be a version earlier than 23, which is incompatible with Espruino.</p>

<p>An alternative to this problem was to execute the following command on the root of the Raspberry Pi Model B in Pidora, third party operating system image:</p>

>$sudo yum install chromium

<p>Unfortunately, same issue resulted from previous attempt.
Our second alternative to the same problem was to execute the following command on the terminal of the Raspberry Pi Model B via Arch Linux:</p>

>$sudo pacman –S chromium

<p>As this attempt again failed we realized that later versions of Chromium were generally not supported by most popular choices of Raspberry Pi’s operating systems.</p>

<p>Then we decided to create a virtual environment of Raspbian under an uBuntu system, and then build Chromium in this embedded system. The following codes were executed in our virtual environment:
</p>

<p>Setting Up the Environment:</p>

>$ git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
>
>$ export PATH=’pwd’/depot_tools:”$PATH”

<p>Creating directory:</p>

>$ mkdir ~/chromium && cd $_

<p>Checking out source code:</p>

>$ fetch --nohooks [--no-history] chromium

<p>Getting necessary Dependencies:</p>

>$ ./build/install-build-deps.sh

<p>Now building Chromium.First, generating the build files:</p>

>$ ./build/gyp_chromium –Dcomponent=shared_library

>$ .build/gyp_chromium –Goutput_dir=out_cros

<p>Building Chrome:</p>

>$ apt-get install ninja-build
>
>$ ninja –C out/Debug chrome

<p>Moving folder where Chromium was built to Raspberry Pi folder to result in obtaining access to Chromium via Raspberry Pi:</p>

>$ sudo mv /usr/root/chromium-build.sh/ /usr/root/raspberrypi/

<p>To our disappointment, an unauthorized message appeared to indicate there was no permission granted to access the raspberry Pi root, therefore, code execution failed to achieve Chromium access in an embedded Raspbian system.</p>

<p>Our last attempt to install Chromium with a different procedure proved unsuccessful, but the good thing is we learned the reason behind our failure: the ARM 7 architecture used by Raspbian is not compatible with Chromium.</p>

<p>The newest Raspberry Pi 2 saved our day. It supports uBuntu and therefore Chromium can be installed as well. The complete procedure takes hundreds lines of code and about two hours, therefore we would like to show you a video from RickMakes “How to Installing Ubuntu 14.04 on a Raspberry Pi 2”. After successfully installed uBuntu, execute the following command should get you the latest version of Chromium without trouble!</p>

>$sudo apt-get install chromium

Reference:
https://code.google.com/p/chromium/wiki/LinuxBuildInstructions
http://dev.chromium.org/developers/how-tos/get-the-code
https://www.youtube.com/watch?v=UGSQ7nzVCs4
