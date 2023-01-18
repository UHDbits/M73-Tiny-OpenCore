<div align="center">

  # **OpenCore 0.8.8 for the Lenovo ThinkCentre M73 Tiny and legacy macOS/OS X**
  
  [![OpenCore 0.8.8](https://img.shields.io/badge/OpenCore-0.8.8-004852)](https://github.com/acidanthera/OpenCorePkg)
  ![Partially Supported Versions: OS X 10.8.3 - 10.10.5](https://img.shields.io/badge/Partially%20Supported%20Versions-OS%20X%2010.8.3%20--%2010.10.5-00466B)
  ![Fully Supported Versions: macOS/OS X 10.11 - 10.14.6](https://img.shields.io/badge/Fully%20Supported%20Versions-OS%20X%2FmacOS%2010.11%20--%2010.14.6-67320A)
  [![Maintained? No.](https://img.shields.io/badge/Maintained%3F-No.-772518)](https://github.com/UHDbits/M73-Tiny-OpenCore/commits/legacy)

  [![Download](https://img.shields.io/badge/Download-114B14?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48cGF0aCBkPSJNNC45NyAxMS4wM2EuNzUuNzUgMCAxIDEgMS4wNi0xLjA2TDExIDE0Ljk0VjIuNzVhLjc1Ljc1IDAgMCAxIDEuNSAwdjEyLjE5bDQuOTctNC45N2EuNzUuNzUgMCAxIDEgMS4wNiAxLjA2bC02LjI1IDYuMjVhLjc1Ljc1IDAgMCAxLTEuMDYgMGwtNi4yNS02LjI1Wm0tLjIyIDkuNDdhLjc1Ljc1IDAgMCAwIDAgMS41aDE0LjVhLjc1Ljc1IDAgMCAwIDAtMS41SDQuNzVaIiBzdHlsZT0iZmlsbDojZmZmZmZmIj48L3BhdGg+PC9zdmc+)](https://github.com/UHDbits/M73-Tiny-OpenCore/releases/tag/v0.8.8-legacy)

  <img src="https://github.com/UHDbits/M73-Tiny-OpenCore/raw/legacy/Resources/Images/ThinkCentre.png" alt="ThinkCentre M73 Tiny" width="400px"/>
  
  | ![Mountain Lion About This Mac](/Resources/Images/About%20This%20Mac/MountainLionAboutThisMac.png) | ![Mojave About This Mac](/Resources/Images/About%20This%20Mac/MojaveAboutThisMac.png) |
  | ----------------------------------------- | ----------------------------------------- |
  
  ## ⚠️ WARNING ⚠️
  
  **It is NOT recommended to use prebuilt OpenCore configurations. They might not work with the exact hardware of your computer, may have features enabled that you don't want, may be outdated, and are harder to diagnose. This configuration is meant to be used as a guide to help you create your own OpenCore configuration for this ThinkCentre, but it can be used as is, only at your own risk.**
  
  ## Contents
  
  [**System Specifications**](#system-specifications)

  [**Directions**](#directions)

  [**Updating OpenCore/macOS/OS X**](#updating-opencoremacosos-x)

  [**Known Issues**](#known-issues)
  
  ## System Specifications
  
  | Component | Model |
  | :-: | :-: |
  | CPU | Intel Core i7-4785T (4c8t) @ 2.20GHz |
  | RAM | 2x8GB (16GB) of DDR3-1600 |
  | GPU | Intel HD Graphics 4600 |
  | Storage | SanDisk Ultra 512GB SSD |
  | Audio | Realtek ALC283 (known issues) |
  | Internal WiFi/Bluetooth | Intel Centrino Wireless-N 7260 (not working) |
  | USB WiFi | TP-Link Archer T3U (driver not included, can be found [here](https://github.com/chris1111/Wireless-USB-Adapter)) |
  | Ethernet | Intel I217-V |
  
  **If your system does not match these specifications (other than the not-important parts, like the WiFi card), it is not guaranteed that this configuration will work for you. If you are unable to get it working, you can create an issue and I will try to help you to the best of my ability.**

  ## Directions
  
  **Follow the steps below by going to the links and following the directions listed. If a step is labeled with a &#42;, that means it's optional, but extremely recommended.**

  | Step # | Link/Directions |
  | :-: | :-: |
  | 0.5 | [For ThinkCentre M93p users, map your USB ports on Windows or WinPE using this tool. Make sure to enable "Use Native Classes" and "Use Legacy Native Classes" in Settings, and use "iMac14,1" as the model identifer.](https://github.com/USBToolBox/tool)
  | 1 | [Creating the USB (Do not move the EFI folder. ProperTree is not needed.)](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/#making-the-installer) |
  | 2 | Move the "EFI" folder from this repository to the "EFI" partition on macOS/OS X, to the root of your USB drive on Windows, or to the "OPENCORE" partition on Linux. Make sure to move the whole folder itself, not just the files inside of the folder.
  | 3 | [Modify your BIOS settings according to this document. Skip "VT-d" if you do not see it in your BIOS.](/Resources/Documentation/BIOSSettings.md)
  | 4 | [Installation Process (Skip "Double checking your work". Check "OpenCore Multiboot Guide" if you want to multiboot.)](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html)
  | 5* | [Moving OpenCore from USB to macOS/OS X Drive (Skip the "Legacy" part at the bottom)](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html)
  | 6* | [Fixing iMessage and other services with OpenCore (This is extremely recommended even if you don't use iServices, because otherwise you will have a generic serial number which isn't the best idea.)](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html)

  ## Updating OpenCore/macOS/OS X
  
  ### Updating OpenCore with a newer version of this configuration
  **If you want to update OpenCore with a newer version of this configuration, just download the new EFI folder, mount the EFI partition, and copy the folder to the partition. Note, if you've made any changes to the configuration, make sure to remember them or save them somewhere because any changes made will be overwritten.**

  ### Updating OpenCore/macOS/OS X manually
  **If you want to update OpenCore manually, you can follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/update.html#updating-opencore) (harder to follow, but recommended and tells you how to update macOS/OS X), or follow [this guide](https://www.insanelymac.com/forum/topic/347035-guide-updating-and-maintaining-opencore-new-method/) (easier to follow, but not recommended.)**

  ## Known Issues

  ### No VGA Output
  **Due to macOS/OS X not offically supporting VGA, you will not be able to output the GUI via the VGA port featured on the ThinkCentre. At the moment, this is currently impossible to fix.**

  ### HD4400 Glitching and Freezing
  **The HD4400 has many issues in macOS/OS X. For example, some random freezes may happen, icons may get replaced, and possibly more. In newer versions of macOS, this can make the system almost unusable. This is impossible to fix at the moment, and the only thing you can do is upgrade your CPU to one with an HD4600 iGPU.**

  ### No Sound in Yosemite and Below
  **In Yosemite and below, sound does not seem to work. This is strange, because AppleALC should work fine in 10.8 Mountain Lion and higher (but the ALC283 only supports Mavericks and higher). You could try to use VoodooHDA to get sound working, but I was also unable to get sound working with VoodooHDA.**

  ### No Ethernet in Mavericks and Below
  **In Mavericks and below, ethernet does not work with the Intel-I217V. In Mavericks, which supports IntelMausi.kext, sometimes an "Ethernet" network will show up in System Preferences, but even with a cable connected it doesn't seem to work. In Mountain Lion, which only supports IntelSnowMausi.kext, the same thing happens. Please let me know if you find a fix to this issue.**
  
  ### No Microphone Jack Input
  **Out of the box, there is no microphone jack input with this configuration. It is possible to get microphone jack input by changing the AppleALC layout ID to 66 using [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/audio.html#making-layout-id-more-permanent), but this results in distorted headphone audio. This can be fixed by going to System Preferences -> Sound, and moving the "Balance" slider left or right. Due to the distorted headphone audio, this configuration is not setup for microphone jack input out of the box. The combo jack (labeled as the headphone jack) is not affected by this issue, and works fine out of the box.**
  
  ![Move the "Balance" slider left or right](/Resources/Images/Headphones%20Fix/HeadphonesFix.png)

  [**Jump to Top**](#opencore-088-for-the-lenovo-thinkcentre-m73-tiny-and-legacy-os-xmacos)

</div>
