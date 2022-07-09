<div align="center">
  
  ### **NOTE: This is an experimental config for macOS 13 Ventura. Although it should work fine, you will NOT have graphics acceleration. This makes macOS basically unusable because of how slow it is. Do not use Ventura on this ThinkCentre as your daily for the time being.**

  # **OpenCore 0.8.3 EFI for the ThinkCentre M73 Tiny**
  
  [![OpenCore 0.8.3](https://img.shields.io/badge/OpenCore-0.8.3-15b8d7)](https://github.com/acidanthera/OpenCorePkg)
  [![macOS Catalina 10.15 to Ventura 13.0](https://img.shields.io/badge/macOS-Catalina%2010.15%20to%20Ventura%2013.0-f48003?logo=apple)](https://apple.com/macos/macos-ventura-preview)
  [![Maintained? Yes!](https://img.shields.io/badge/Maintained%3F-Yes!-green.svg)](https://github.com/UHDbits/M73-Tiny-OpenCore/graphs/commit-activity)

  [![Config for legacy Mac OS X/macOS here](https://img.shields.io/badge/Click%20here%20for%20legacy%20Mac%20OS%20X%2FmacOS%20support.-red)](https://github.com/UHDbits/M73-Tiny-OpenCore/tree/legacy)

  <img src="https://github.com/UHDbits/M73-Tiny-OpenCore/raw/main/Images/ThinkCentre.png" alt="ThinkCentre M73 Tiny" width="400px"/>
  
  | ![Catalina About This Mac](/Images/About%20This%20Mac/DarkCatalinaAboutThisMac.png#gh-dark-mode-only) ![Catalina About This Mac](Images/About%20This%20Mac/LightCatalinaAboutThisMac.png#gh-light-mode-only) | ![Ventura About This Mac](/Images/About%20This%20Mac/DarkVenturaAboutThisMac.png#gh-dark-mode-only) ![Ventura About This Mac](/Images/About%20This%20Mac/LightVenturaAboutThisMac.png#gh-light-mode-only) |
  | ----------------------------------------- | ----------------------------------------- |
  
  ## ⚠️ WARNING ⚠️
  
  **I do NOT recommend using prebuilt OpenCore EFIs. They might not work with the exact configuration of your computer, may have features enabled that you don't want, may be outdated, and are harder to diagnose. This is meant to be used to help with the creation of a custom OpenCore EFI, or should only be used at your own risk.**
  
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
  | 5 | [(FOR VENTURA ONLY, AND CURRENTLY DOES NOT WORK) Use OpenCore Legacy Patcher to patch the root volume to get graphics acceleration.](https://dortania.github.io/OpenCore-Legacy-Patcher/POST-INSTALL.html#applying-post-install-volume-patches)
  | 6** | [Moving OpenCore from USB to macOS Drive (Skip legacy part at the bottom)](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html)
  | 7** | [Fixing iMessage and other services with OpenCore (This is extremely recommended even if you don't use iServices, because otherwise you will have a generic serial number which isn't the best idea.)](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html)
  | 8* | [For ThinkCentre M93p users, map your USB ports using this tool (check issues for instructions after step 5). Make sure to delete the previous USBMap.kext.](https://github.com/corpnewt/USBMap)

  ## Updating OpenCore/macOS
  
  ### Updating OpenCore with a newer version of my config
  **If you want to upgrade OpenCore with a newer version of my config, just download the new EFI folder, mount the EFI partition, and copy it over. Note, if you've made any changes to the config, make sure to save them in a text document because these changes will be overwritten.**

  ### Updating OpenCore/macOS manually
  **If you want to update OpenCore manually, you can follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/update.html#updating-opencore) (harder to follow, but recommended and tells you how to upgrade macOS), or follow [this guide](https://www.insanelymac.com/forum/topic/347035-guide-updating-and-maintaining-opencore-new-method/) (easier to follow, but not recommended.)**

  ## Known Issues

  ### Monterey 12.3+ crashes during setup
  **Monterey 12.3 and newer crashes during the "Migration Assistant" part of setup. Sometimes, you can get past the screen, but it'll freeze later. This is due to the HD4400, and can only be fixed by upgrading your CPU to one with an HD4600 iGPU. It is also unknown if this happens in Ventura.**

  ### HD4400 Glitching and Freezing
  **The HD4400 has many issues in macOS. For example, some icons may be missing (image below), some random freezes may happen, icons may get replaced, and more. In newer versions of macOS, this can make the system almost unusable. This is impossible to fix at the moment, and the only thing you can do is upgrade your CPU to one with an HD4600 iGPU.**

  ![Example of Missing Icons](/Images/Missing%20Icons/DarkMissingIcons.png#gh-dark-mode-only) ![Example of Missing Icons](Images/Missing%20Icons/LightMissingIcons.png#gh-light-mode-only)

  ### Headphone Audio Glitching
  **Out of the box, you may notice that audio through headphones is inaudible. This is a glitch with AppleALC and can be fixed by going into System Preferences -> Audio, and by moving the "Balance" slider left or right. This will not change the actual balance of the headphones, but it will fix the issue.**

  ![Move the "Balance" slider left or right](/Images/Headphones%20Fix/DarkHeadphonesFix.png#gh-dark-mode-only) ![Move the "Balance" slider left or right](/Images/Headphones%20Fix/LightHeadphonesFix.png#gh-light-mode-only)

  ### No Microphone Jack Input
  **Out of the box, there is no Microphone Jack input with this config. It should be possible to get Microphone Jack input by changing the AppleALC layout-id to 66 using [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/audio.html#making-layout-id-more-permanent), but this apparently results in much worse output audio quality. You could also try using VoodooHDA, but the same issue happens, much worse output audio quality. I have decided that better output audio quality is more important then being able to input something through the Microphone Jack, so I have done that instead.**
  
  [**Jump to Top**](#opencore-083-efi-for-the-thinkcentre-m73-tiny)

</div>
