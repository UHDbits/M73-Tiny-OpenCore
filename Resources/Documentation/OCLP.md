# **OpenCore Legacy Patcher Tutorial**

### **IMPORTANT NOTICE:** 
### **Although graphics acceleration is now possible on macOS 13 Ventura and macOS 14 Sonoma, there are some minor issues. To check the issues that affect this ThinkCentre, check [this link](https://github.com/dortania/OpenCore-Legacy-Patcher/issues/1008/) and look for "Haswell" in "Known Issues". If any of these issues affect you, it is recommended to stay on Monterey or older. Also, updating macOS can break root patches, so please check various sources to see if the latest version of Ventura or Sonoma supports OpenCore Legacy Patcher before updating.**

## Contents

[**First Time Setup**](#first-time-setup)
  
[**Before Updating macOS**](#before-updating-macos)

[**After Updating macOS**](#after-updating-macos)

## First Time Setup

**After installing macOS and going through the initial setup, follow the steps below to get graphics acceleration.**

1. Reboot your ThinkCentre into the OpenCore boot menu. After you see your boot options, one of which should be your macOS drive, press the spacebar. Move over to the "Reset NVRAM" option, and press "Enter". Wait for your computer to reboot back into macOS, and then sign into your account.
2. Download the latest OpenCore Legacy Patcher version from [this link](https://github.com/dortania/OpenCore-Legacy-Patcher/releases/latest). After downloading and extracting the .zip, open the app.
3. After opening OpenCore Legacy Patcher, press the "Post Install Root Patch" option. You should see that "Graphics: Intel Haswell" is the only available patch, unless you have a supported WiFi card, in which case you will also see "Networking: Modern Wireless". Press the "Start Root Patching" button. You will have to enter your password to continue the process. You may also see a prompt asking you to open "System Settings", but this can be safely ignored. After patching is done, you will be able to restart. Once you boot back into macOS, you should notice that you have transparency and that the system is much faster. Congratulations, you now have graphics acceleration!
4. To prevent your system from breaking due to automatic updates, sign in to your account and open "System Settings -> General -> Software Update". Click on the information icon in the top right corner. Make sure "Install macOS Updates" is disabled. Congratulations, you can now use your ThinkCentre!

## Before Updating macOS

**If you want to update to a new version of macOS 13.x.x Ventura or macOS 14.x.x Sonoma, follow these steps below to make sure that it will work without issues.**

1. Check various sources to see if the new macOS version is supported, like the [OCLP Discord](https://discord.gg/rqdPgH8xSN), [@khronokernel's Twitter account](https://twitter.com/khronokernel), [the macOS 13 Ventura on Unsupported Macs forum thread](https://forums.macrumors.com/threads/macos-13-ventura-on-unsupported-macs-thread.2346881/), [the macOS 14 Sonoma on Unsupported Macs forum thread](https://forums.macrumors.com/threads/macos-14-sonoma-on-unsupported-macs-thread.2391630/), and/or [the OCLP issues page](https://github.com/dortania/OpenCore-Legacy-Patcher/issues). You can also check to see if the latest macOS version is confirmed to be functioning on this ThinkCentre by looking at the top of the README.md of this repository. This isn't always updated immediately though, so it may be slightly out of date.
2. If you do not find any info on the new macOS version, **do not ask if it is supported.** Instead, wait for information to come out on if it is supported.
3. If you find info that says the new macOS version is not supported with OCLP, **do not update.** You will lose graphics acceleration and possibly WiFi support until support is added, which means your system will be unusably slow unless you reinstall macOS or wait for support to be added. Instead, check back every once in a while on those websites to see if support has been added.
4. Once you find info that shows the new macOS version is supported with OCLP, make sure it is supported on the latest stable version of OCLP. Otherwise, the patches may not be finished or released to the public yet. If you find out that it is supported by the latest stable release of OCLP, you are now free to update to the latest macOS version. You might want to make sure to download the latest OCLP version from [this link](https://github.com/dortania/OpenCore-Legacy-Patcher/releases/latest) before updating, because it is possible you will lose WiFi connectivity after the update until you patch again.

## After Updating macOS

**After following the steps above to make sure that the macOS version you want to update to is supported, and after updating, follow these steps to regain graphics acceleration.**

1. You will likely see a prompt from OpenCore Legacy Patcher asking you to apply root patches again. Before continuing, it will ask you to make sure that you are using the latest version of OCLP. Check [this link](https://github.com/dortania/OpenCore-Legacy-Patcher/releases/latest) to ensure you have the latest version. If you are using an outdated version, download the latest version, and open the app once it is finished downloading. If you have the latest version, press "Ok" on the prompt asking you to apply root patches.
2. After opening OpenCore Legacy Patcher, press the "Post Install Root Patch" option. You should see that "Graphics: Intel Haswell" is the only available patch, unless you have a supported WiFi card, in which case you will also see "Networking: Modern Wireless". Press the "Start Root Patching" button. You will have to enter your password to continue the process. You may also see a prompt asking you to open "System Settings", but this can be safely ignored. After patching is done, you will be able to restart. Congratulations, you now have graphics acceleration again! 
