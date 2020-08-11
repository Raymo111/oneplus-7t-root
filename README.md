# How to Root OnePlus 7T with Magisk
#### By Raymo111
*Last updated 10 August 2020*

So, like me, you've just got your OnePlus 7T. You want to root it, because OnePlus is the only phone manufacturer amazing like that. That's what you should do, at least in my opinion. P.S. If you are here before you got it: wow, good for you. Pro tip, use https://oneplusstock.net/ to make sure you get it immediately when OnePlus releases a new batch.

## Notes
- I'm writing this tutorial as I do it myself, both for my sake in case I need to do this in the future, and so I get everything, without missing something, to you.
- OOS = Oxygen OS and OB = Open Beta of OOS (took me a while to figure out the second one)
- If anything goes wrong:
  - I'm not responsible
  - https://www.oneplus.com/global/support/softwareupgrade > OnePlus 7T (**not 7T Pro!**) has the stock boot image that you can flash using fastboot the same way you flash a patched version.
 - In case 10.0.0.12 isn't the newest version anymore and xda-devs doesn't have a patched **GLOBAL** version of the latest OOS then [this xda post](https://forum.xda-developers.com/showpost.php?p=81277507&postcount=613) might help. (I also just saved it on wayback machine just in case)

## Step 1: Setup and update
1. Remove all packaging from your phone, but **don't put the included case on yet**. It's a pain to put on and you'll thank me in a few minutes.
2. Go through setup. Keep in mind you may have to do this again later. I'm not sure.
3. After you get to the part where OnePlus tells you to insert your SIM, now you can put the case on. Tip: put the top right corner on last :) Oh, and you're welcome!
4. Download the latest versions of [ADB](https://developer.android.com/studio/releases/platform-tools) and a Magisk-patched boot image for OnePlus 7T. (OOS 10.0.12, the latest version as of the 10 August 2020, is [included in this repo](Magisk-patched OOS_10_0_12.img).
5. If you're on windows, extract the ADB zip file to C:\adb. Open cmd there.
