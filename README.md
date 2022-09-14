<div align="right">
  
  ### **NOTE: macOS Ventura currently does NOT work on this config. If you want a WIP version of this config that works with Ventura, check the "ventura" branch. Currently, graphics acceleration is in alpha stages, so it can be buggy and unstable. It is not recommended to use Ventura on this ThinkCentre until the main branch has been updated to support Ventura. Please check [this issue](https://github.com/UHDbits/M73-Tiny-OpenCore/issues/1) for more info.**

  # **OpenCore 0.8.4 for the Lenovo ThinkCentre M73 Tiny**
  
  [![OpenCore 0.8.4](https://img.shields.io/badge/OpenCore-0.8.4-15b8d7)](https://github.com/acidanthera/OpenCorePkg)
  ![macOS Catalina 10.15 to Monterey 12.5](https://img.shields.io/badge/macOS-Catalina%2010.15%20to%20Monterey%2012.5-blueviolet?logo=apple)
  [![Maintained? Yes!](https://img.shields.io/badge/Maintained%3F-Yes!-green.svg)](https://github.com/UHDbits/M73-Tiny-OpenCore/graphs/commit-activity)

  [![Configuration for legacy Mac OS X/macOS here](https://img.shields.io/badge/Click%20here%20for%20legacy%20Mac%20OS%20X%2FmacOS%20support.-red)](https://github.com/UHDbits/M73-Tiny-OpenCore/tree/legacy)

  <img src="https://github.com/UHDbits/M73-Tiny-OpenCore/raw/main/Resources/Images/ThinkCentre.png" alt="ThinkCentre M73 Tiny" width="400px"/>
  
  | ![Catalina About This Mac](/Resources/Images/About%20This%20Mac/DarkCatalinaAboutThisMac.png#gh-dark-mode-only) ![Catalina About This Mac](/Resources/Images/About%20This%20Mac/LightCatalinaAboutThisMac.png#gh-light-mode-only) | ![Monterey About This Mac](/Resources/Images/About%20This%20Mac/DarkMontereyAboutThisMac.png#gh-dark-mode-only) ![Monterey About This Mac](/Resources/Images/About%20This%20Mac/LightMontereyAboutThisMac.png#gh-light-mode-only) |
  | ----------------------------------------- | ----------------------------------------- |
  
  ## ⚠️ WARNING ⚠️
  
  **It is NOT recommended to use prebuilt OpenCore configurations. They might not work with the exact hardware of your computer, may have features enabled that you don't want, may be outdated, and are harder to diagnose. This configuration should only be used at your own risk, or as a guide to help you create your own configuration.**
  
  ## Contents
  
  [**System Specifications**](#system-specifications)

  [**Directions**](#directions)

  [**Updating OpenCore/macOS**](#updating-opencoremacos)

  [**Known Issues**](#known-issues)
  
  ## System Specifications
  
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
  
  **If your system does not match these specifications (other than the not-important parts, like the WiFi card), it is not guaranteed that this configuration will work for you. If you are unable to get it to work, you can create an issue and I will try to help you to the best of my ability.**

  ## Directions
  
  **Follow the steps below by going to the links and following the directions on the OpenCore Install Guide. If a step is labeled with a &#42;, it means it's optional, but extremely recommended.**

  | Step # | Link/Directions |
  | :-: | :-: |
  | 0.5 | [For ThinkCentre M93p users, map your USB ports on Windows or WinPE using this tool. Make sure to enable "Use Native Classes" in Settings, and use "iMac17,1" as the model identifer.](https://github.com/USBToolBox/tool)
  | 1 | [Creating the USB (Do not move the EFI folder. ProperTree is not needed.)](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/#making-the-installer) |
  | 2 | Move the "EFI" folder from this repository into the "EFI" partition on macOS, to the root of your USB drive on Windows, or to the "OPENCORE" partition on Linux. Make sure to move the whole folder itself, not just the files inside of the folder.
  | 3 | [Modify your BIOS settings according to this document. Skip "VT-d" if you do not see it in your BIOS.](/Resources/Documentation/BIOSSettings.md)
  | 4 | [Installation Process (Skip "Double checking your work". Check "OpenCore Multiboot Guide" if you want to multiboot.)](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html)
  | 5* | [Moving OpenCore from USB to macOS Drive (Skip the "Legacy" part at the bottom.)](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html)
  | 6* | [Fixing iMessage and other services with OpenCore (This is extremely recommended even if you don't use iServices, because otherwise you will have a generic serial number which isn't a good idea.)](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html)
  

  ## Updating OpenCore/macOS
  
  ### Updating OpenCore with a newer version of the configuration
  **If you want to upgrade OpenCore with a newer version of the configuration, just download the new EFI folder, mount the EFI partition, and copy it over. Note, if you've made any changes to the configuration, make sure to save them in a text document because these changes will be overwritten.**

  ### Updating OpenCore/macOS manually
  **If you want to update OpenCore manually, you can follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/update.html#updating-opencore) (harder to follow, but recommended and tells you how to upgrade macOS), or follow [this guide](https://www.insanelymac.com/forum/topic/347035-guide-updating-and-maintaining-opencore-new-method/) (easier to follow, but not recommended.)**

  ## Known Issues
  
  ### No VGA Output
  **With macOS, you will not be able to output the GUI via the VGA port featured on the ThinkCentre. This is an issue with macOS not offically supporting VGA, and at the moment is currently impossible to fix.**

  ### Monterey 12.3+ crashes during setup on the HD4400
  **Monterey 12.3 or newer crashes during the "Migration Assistant" part of setup. Sometimes, you can get past the screen, but it'll freeze later. This is due to the HD4400, and can only be fixed by upgrading your CPU to one with an HD4600 iGPU.**

  ### HD4400 Glitching and Freezing
  **The HD4400 has many issues in macOS. For example, some icons may be missing (image below), random freezes may happen, icons may get replaced, or more. In newer versions of macOS, this can make the system almost unusable. This is impossible to fix at the moment, and the only thing you can do is upgrade your CPU to one with an HD4600 iGPU.**

  ![Example of Missing Icons](/Resources/Images/Missing%20Icons/DarkMissingIcons.png#gh-dark-mode-only) ![Example of Missing Icons](/Resources/Images/Missing%20Icons/LightMissingIcons.png#gh-light-mode-only)

  ### Headphone Audio Glitching
  **Out of the box, you may notice that audio through headphones is inaudible. This is a glitch with AppleALC and can be fixed by going into System Preferences -> Sound, and by moving the "Balance" slider left or right. This will not change the actual balance of the headphones, but it will fix the issue.**

  ![Move the "Balance" slider left or right](/Resources/Images/Headphones%20Fix/DarkHeadphonesFix.png#gh-dark-mode-only) ![Move the "Balance" slider left or right](/Resources/Images/Headphones%20Fix/LightHeadphonesFix.png#gh-light-mode-only)
  
  ### No Microphone Jack Input
  **Out of the box, there is no microphone jack input with this config. It should be possible to get audio input by changing the AppleALC layout-id to 66 using [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/audio.html#making-layout-id-more-permanent), but this results in much worse output audio quality. You could also try using VoodooHDA, but this would also result in much worse output audio quality. Due to the worse audio quality, this configuration is not setup for audio input out of the box. USB Microphones are not affected by this issue.**

  [**Jump to Top**](#opencore-084-for-the-lenovo-thinkcentre-m73-tiny)

</div>
