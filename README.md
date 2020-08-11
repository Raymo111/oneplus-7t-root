# How to Root OnePlus 7T with Magisk
#### By Raymo111
*Last updated 10 August 2020*

So, like me, you've just got your OnePlus 7T. You want to root it, because OnePlus is the only phone manufacturer amazing like that. That's what you should do, at least in my opinion. P.S. If you are here before you got it: wow, good for you. Pro tip, use https://oneplusstock.net/ to make sure you get it immediately when OnePlus releases a new batch.

## Notes
- I'm writing this tutorial as I do it myself, both for my sake in case I need to do this in the future, and so I get everything, without missing something, to you.
- OOS = Oxygen OS and OB = Open Beta of OOS (took me a while to figure out the second one)
- If anything goes wrong:
  - I'm not responsible
  - Try rebooting first before you smash something in anger. If you do smash something, don't smash something expensive.
  - https://www.oneplus.com/global/support/softwareupgrade > OnePlus 7T (**not 7T Pro!**) has the stock boot image that you can flash using fastboot the same way you flash a patched version.
 - In case 10.0.0.12 isn't the newest version anymore and xda-devs doesn't have a patched **GLOBAL** version of the latest OOS then [this xda post](https://forum.xda-developers.com/showpost.php?p=81277507&postcount=613) might help. (I also just saved it on wayback machine just in case)

## Step 1: Setup and update
1. Remove all packaging from your phone, but **don't put the included case on yet**. It's a pain to put on and you'll thank me in a few minutes.
2. Go through setup. Keep in mind you may have to do this again later. Maybe. Oh, and don't bother with biometrics (i.e. fingerprint or face unlock) because you'll be removing those in a minute.
3. After you get to the part where OnePlus tells you to insert your SIM, now you can put the case on. Tip: put the top right corner on last :) Oh, and you're welcome!
4. Download the latest versions of [ADB](https://developer.android.com/studio/releases/platform-tools) and a Magisk-patched boot image for OnePlus 7T. (OOS 10.0.12, the latest version as of the 10 August 2020, is [included in this repo](https://github.com/Raymo111/oneplus-7t-root/raw/master/Magisk-patched%20OOS_10_0_12.img).
5. If you're on windows, extract the ADB zip file to C:\adb. Open cmd there. Otherwise, add adb to your path or open up a terminal where adb is.
6. Head over to `Settings > About phone`. Tab on the Build number at least 7 times to get developer access.
7. Note your build number. **If it isn't the latest (i.e. > 10.0.12) then you'll need to `System > System updates > update` your OOS. If you don't you risk bricking or bootlooping. At the very least, wifi won't work. Believe me, I tried.**
8. Once that's up to date, head over to `Security & lock screen` and set `Screen lock` to `none`. Go to `System > Developer options` and enable `Advanced reboot`, `USB debugging` and `OEM unlocking`. It sounds scary but you gotta do it if you wanna root.
9. Plug your phone into your computer and enable USB debugging when it pops up on your phone. I would set it to `always enable`. If you want to do that now just unplug and replug :)
10. In the terminal you opened (yes cmd is a terminal), run
```
adb devices
```
If the device doesn't show up then you skipped some section of the tutorial. Or something else that I have no idea. Feel free to create an issue to this repo and I *might* help you out.
11. Assuming it does show up, you can hold the power button on your phone and reboot to Bootloader (tap it when the options pop up). If you like running commands you can also use
```
adb reboot bootloader
```
12. You should see a hacker-like screen on your phone. Run
```
fastboot oem unlock
```
13. Use the volume keys to select the unlock bootloader option, and power key to confirm.
14. If your phone reboots, verify that adb is still active (with the `devices` command) and go back to fastboot.
15. Boot the patched OEM image with
```
fastboot boot path-to-magisk_patched.img
```
If the phone doesn't automatically reboot, run
```
fastboot reboot
```
13. Head over to https://magiskmanager.com/downloading-magisk-manager on your phone and download Magisk Manager. If you can't connect to Wi-Fi then you messed up. Now might be a little late to read my [notes](#Notes), but better late than never.
14. Install Magisk manager, enabling APK installation on your phone if you need to.
