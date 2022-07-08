<div align="center">
  
  ### **NOTE: macOS Ventura currently does NOT work on this config. If you want to get a WIP version of this config that works with Ventura, check the "ventura" branch. Currently, graphics acceleration is not supported, so it is unusable. I do not recommend using Ventura on this ThinkCentre until this main branch has been updated to support Ventura.**

  # **OpenCore 0.8.2 EFI for the ThinkCentre M73 Tiny**
  
  [![OpenCore 0.8.2](https://img.shields.io/badge/OpenCore-0.8.2-15b8d7)](https://github.com/acidanthera/OpenCorePkg)
  [![macOS Monterey 12.5](https://img.shields.io/badge/macOS-Monterey%2012.5-blueviolet?logo=apple)](https://apple.com/macos/monterey)
  [![Maintained? Yes!](https://img.shields.io/badge/Maintained%3F-Yes!-green.svg)](https://github.com/UHDbits/M73-Tiny-OpenCore/graphs/commit-activity)

  <img src="https://github.com/UHDbits/M73-Tiny-OpenCore/raw/main/Images/ThinkCentre.png" alt="ThinkCentre M73 Tiny" width="400px"/>
  
  | ![Catalina About This Mac](/Images/About%20This%20Mac/DarkCatalinaAboutThisMac.png#gh-dark-mode-only) ![Catalina About This Mac](Images/About%20This%20Mac/LightCatalinaAboutThisMac.png#gh-light-mode-only) | ![Monterey About This Mac](/Images/About%20This%20Mac/DarkMontereyAboutThisMac.png#gh-dark-mode-only) ![Monterey About This Mac](/Images/About%20This%20Mac/LightMontereyAboutThisMac.png#gh-light-mode-only) |
  | ----------------------------------------- | ----------------------------------------- |
  
  ## ⚠️ WARNING ⚠️
  
  **I do NOT recommend using prebuilt OpenCore EFIs. They might not work with the exact configuration of your computer, may have features enabled that you don't want, may be outdated, and are harder to diagnose. This is meant to be used to help with the creation of a custom OpenCore EFI, or should only be used at your own risk. Also, it may not work with your macOS/OS X version. It should work on anything since OS X 10.8 Mountain Lion, but it's only been tested on macOS 10.14 Mojave and above.**
  
  ## Contents
  
  [**My System Specifications**](#my-system-specifications)

  [**Directions**](#directions)

  [**Updating OpenCore/macOS**](#updating-opencoremacos)

  [**Known Issues**](#known-issues)
  
  ## My System Specifications
  
  | Component | Model |
  | :-: | :-: |
  | CPU | Intel Core i7-4785T (4c8t) @ 2.20GHz |
  | RAM | 2x8GB (16GB) of DDR3-1600 |
  | GPU | Intel HD Graphics 4600 |
  | Storage | SanDisk Ultra 512GB SSD |
  | Audio | Realtek ALC283 (known issues) |
  | Internal WiFi/Bluetooth | Intel Centrino Wireless-N (not working) |
  | USB WiFi | TP-Link Archer T3U (driver not included, can be found [here](https://github.com/chris1111/Wireless-USB-OC-Big-Sur-Adapter)) |
  | Ethernet | Intel I217-V |
  
  **If your system does not meet these exact specifications (other than the not-important parts, like the WiFi card), I can not guarantee this config will work for you. If you try it, and it doesn't work for you, you can create an issue and I will try to help you make it work.**

  ## Directions
  
  **Follow the steps below by going to the links and following the according directions on the OpenCore guide. The step is optional (but may be required to get some features working) if it is labeled with a &#42;. If the step labeled has &#42;&#42;, that means it's optional, but extremely recommended.**

  | Step # | Link/Directions |
  | :-: | :-: |
  | 1 | [Creating the USB (do not put the EFI folder in the EFI partition, and do not download "OpenCorePkg").](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/#making-the-installer) |
  | 2 | Mount your EFI partition if not already done, and take the "EFI" folder in this repo and copy it into the EFI partition. Make sure you copy the "EFI" folder itself, and not the folders inside of it directly into the EFI partition.
  | 3 | [Intel BIOS Settings (scroll to the bottom of this page if not done already, and Disable/Enable as many of the settings as possible. If it tells you to enable anything in the actual OpenCore config, ignore it.)](https://dortania.github.io/OpenCore-Install-Guide/config.plist/haswell.html#intel-bios-settings)
  | 4 | [Installation Process (skip "Double checking Your Work". Check "OpenCore Multiboot Guide" if you want to multiboot.)](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html)
  | 5** | [Moving OpenCore from USB to macOS Drive (Skip legacy part at the bottom)](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html)
  | 6** | [Fixing iMessage and other services with OpenCore (This is extremely recommended even if you don't use iServices, because otherwise you will have a generic serial number which isn't the best idea.)](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html)
  | 7* | [For ThinkCentre M93p users, map your USB ports using this tool (check issues for instructions after step 5). Make sure to delete the previous USBMap.kext.](https://github.com/corpnewt/USBMap)

  ## Updating OpenCore/macOS
  
  ### Updating OpenCore with a newer version of my config
  **If you want to upgrade OpenCore with a newer version of my config, just download the new EFI folder, mount the EFI partition, and copy it over. Note, if you've made any changes to the config, make sure to save them in a text document because these changes will be overwritten.**

  ### Updating OpenCore/macOS manually
  **If you want to update OpenCore manually, you can follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/update.html#updating-opencore) (harder to follow, but recommended and tells you how to upgrade macOS), or follow [this guide](https://www.insanelymac.com/forum/topic/347035-guide-updating-and-maintaining-opencore-new-method/) (easier to follow, but not recommended.)**

  ## Known Issues

  ### Monterey 12.3+ crashes during setup
  **Monterey 12.3 and newer crashes during the "Migration Assistant" part of setup. Sometimes, you can get past the screen, but it'll freeze later. This is due to the HD4400, and can only be fixed by upgrading your CPU to one with an HD4600 iGPU.**

  ### HD4400 Glitching and Freezing
  **The HD4400 has many issues in macOS. For example, some icons may be missing (image below), some random freezes may happen, icons may get replaced, and more. In newer versions of macOS, this can make the system almost unusable. This is impossible to fix at the moment, and the only thing you can do is upgrade your CPU to one with an HD4600 iGPU.**

  ![Example of Missing Icons](/Images/Missing%20Icons/DarkMissingIcons.png#gh-dark-mode-only) ![Example of Missing Icons](Images/Missing%20Icons/LightMissingIcons.png#gh-light-mode-only)

  ### Headphone Audio Glitching
  **Out of the box, you may notice that audio through headphones is inaudible. This is a glitch with AppleALC and can be fixed by going into System Preferences -> Audio, and by moving the "Balance" slider left or right. This will not change the actual balance of the headphones, but it will fix the issue.**

  ![Move the "Balance" slider left or right](/Images/Headphones%20Fix/DarkHeadphonesFix.png#gh-dark-mode-only) ![Move the "Balance" slider left or right](/Images/Headphones%20Fix/LightHeadphonesFix.png#gh-light-mode-only)
  
  [**Jump to Top**](#opencore-082-efi-for-the-thinkcentre-m73-tiny)

</div>
