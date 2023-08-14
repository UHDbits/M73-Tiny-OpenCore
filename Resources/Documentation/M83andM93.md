# **Adding proper ThinkCentre M83 Tiny and M93p support**

**Although the ThinkCentre M73 Tiny, M83 Tiny, and M93p all have very similar hardware, they do have minor differences, one of the more major ones being the fact that there are many more USB 3.x ports on the M83 Tiny and M93p. This can cause some minor compatibility issues between each of the models, and especially since this configuration is heavily modified to be as lightweight as possible, you may have to make some minor modifications to the configuration to make it work correctly on your model of ThinkCentre. The process is fairly easy, though, and you can follow the short guide below to make the configuration more likely to work on your hardware.**

## Copying prebuilt SSDTs to the configuration folder

**Since the SSDTs included in the configuration have been built specifically for the ThinkCentre M73 Tiny, it may be required to use prebuilt SSDTs that are more bloated but also work with a much wider range of hardware. This is an extremely simple process that can be done in one step listed below.**

1. Copy all of the ".aml" files from the "/Resources/SSDTs/" folder of this configuration, and copy them to the "/EFI/OC/ACPI/" folder. Make sure to select "Replace" when copying the files over to overwrite the already existing files. After this, you are done with copying the prebuilt SSDTs!

## Mapping your USB Ports with USBToolbox

**This step will ensure that your USB 3.x ports work properly in macOS. To perform these steps, you should be on Windows 8 or above, and at the moment, GNU/Linux and macOS are not supported.**

1. Download the latest version of USBToolbox [from here](https://github.com/USBToolBox/tool/releases/latest). You can download the "Windows.exe" file to make the process as easy as possible.
2. Open the "Windows.exe" file, which should open a CMD window with the USBToolbox UI.
3. Type "C" for "Change Settings" and press the Enter key.
4. Type "N" for "Use Native Classes" and press the Enter key. Make sure "Use Native Classes" is now shown as "Enabled" in the menu.
5. Type "B" for "Back" and press the Enter key.
6. Type "D" for "Discover Ports" and press the Enter key. Now, you will have to plug in a USB 1.x/2.x device **and** a USB 3.x device into every USB port. Most mice and keyboards are USB 1.x or 2.x, and many flash drives are USB 3.x. Make sure to unplug your keyboard and mouse from their normal ports while this process is going on unless you are using one of them as a USB 1.x or 2.x device. After this, plug your keyboard and mouse back into your ThinkCentre.
7. Type "B" for "Back" and press the Enter key.
8. Type "S" for "Select Ports and Build Kext" and press the Enter key.
9. All of the populated ports should already be enabled, and all of the empty ports should already be disabled, but, just to be safe, type "P" for "Enable All Populated Ports", press Enter, and type "D" for "Disable All Empty Ports", and press Enter.
10. If you have a Bluetooth module in your computer that is supported in macOS, you may have to change the port type to "255", which stands for "Internal". To do this, find the USB port for your Bluetooth module, and type in "T:port#:255". Let's say my Bluetooth module is under "4.  HS04 | USB 2.0 | Type A (Guessed)", I would enter "T:4:255".
10. Type "K" for "Build USBMap.kext" and press the Enter key.
11. If asked to "Ignore" or "Disable", type "D" for "Disable" and press the Enter key.
12. You will now be asked to enter your model identifier. To do this, type "iMac14,4" and press the Enter key.
13. The "USBMap.kext" will now be created, and will show up in the same folder where "Windows.exe" is located!
14. Go to the "/EFI/OC/Kexts" folder of this configuration, and delete the old "USBMap.kext" from the folder.
15. Copy the "USBMap.kext" that you just made to the "/EFI/OC/Kexts" folder of this configuration. Congratulations, you have now mapped your USB ports!

**After all of this, you should be ready to continue with the directions in the README. If you have any issues, please feel free to make an issue, and I will try to help you out to the best of my ability!**
